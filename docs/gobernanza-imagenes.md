# Gobernanza de Imágenes, Seguridad y Licenciamiento

**Documento de Propuesta de Mejora**

**Fecha:** Julio 2026

---

## 1. Diagnóstico del documento base

El documento original propone un flujo de gestión de imágenes sólido (solicitud → búsqueda en Harbor → escaneo con Trivy → firma → publicación → descarga), pero presenta tres vacíos importantes cuando se piensa en un contexto que evoluciona de universidad a empresa (Fase 2):

1. **Seguridad como evento único, no continuo.** El escaneo con Trivy solo ocurre al crear la imagen. No hay mecanismo para detectar vulnerabilidades descubiertas después de la publicación.
2. **Ausencia total de gestión de licencias.** El flujo solo controla seguridad técnica, pero una imagen puede ser 100% segura y aun así violar los términos de una licencia de software (ej. usar una librería GPL en un producto comercial cerrado).
3. **Sin política de ciclo de vida.** No se define qué pasa con imágenes viejas, no usadas o reemplazadas — el catálogo crecería sin control.

Las siguientes secciones desarrollan propuestas concretas para cerrar estos vacíos.

---

## 2. Propuestas de mejora — Arquitectura Técnica

### 2.1 Gestión de secretos
El stack propuesto (GitLab, Harbor, Keycloak, PostgreSQL, MinIO) maneja credenciales sensibles (tokens de CI/CD, llaves de firma digital, contraseñas de base de datos) que no tienen un lugar definido para almacenarse de forma segura.

**Propuesta:** incorporar un gestor de secretos dedicado — **HashiCorp Vault** (open source, se integra bien con Kubernetes) o, como alternativa más ligera, los *Kubernetes Secrets* nativos combinados con *Sealed Secrets* para poder versionarlos en GitLab de forma segura.

### 2.2 Criterio de elección de distribución de Kubernetes
El documento menciona "K3s/Talos" como si fueran intercambiables, pero tienen propósitos distintos:

| Criterio | K3s | Talos |
|---|---|---|
| Curva de aprendizaje | Baja | Media-alta |
| Nivel de seguridad por defecto | Estándar | Alto (sin shell, inmutable) |
| Recomendado para | Fase 1 (Universitaria) | Fase 2 (Empresa) |

**Propuesta:** usar K3s en la Fase 1 para facilitar el aprendizaje de los estudiantes, y evaluar la migración a Talos en la Fase 2 cuando el foco es seguridad y cumplimiento empresarial.

### 2.3 Observabilidad
El documento no menciona cómo se va a monitorear la plataforma en producción (¿está caído Harbor? ¿cuántas imágenes se descargan por día? ¿hay intentos de acceso no autorizados?).

**Propuesta:** incorporar una capa de observabilidad basada en **Prometheus** (métricas) + **Grafana** (dashboards) + **Loki** (logs), todas herramientas open source compatibles con Kubernetes.

---

## 3. Propuestas de mejora — Gestión de Imágenes y Trazabilidad

### 3.1 Flujo ampliado propuesto

Se propone extender el flujo original de 7 pasos, agregando control continuo y gobernanza de licencias:

1. Solicitud de imagen
2. Búsqueda automática en Harbor
3. Creación/Importación
4. **Escaneo dual: vulnerabilidades (Trivy) + licencias (ver sección 4)**
5. Firma digital y aprobación
6. Publicación con metadatos de trazabilidad
7. Descarga segura por estudiantes
8. **Re-escaneo periódico de imágenes ya publicadas (nuevo)**
9. **Política de retención y deprecación (nuevo)**

### 3.2 Re-escaneo periódico (paso 8)
Una imagen puede pasar el escaneo hoy y ser vulnerable mañana, cuando se descubra una falla nueva en alguna librería que ya contiene.

**Propuesta concreta:** pipeline automático (ej. con GitLab CI programado, o Renovate/Dependabot como ya menciona el documento base para actualizaciones) que re-escanee **todas** las imágenes publicadas cada semana, y notifique automáticamente al Responsable de Imágenes si aparece una vulnerabilidad crítica nueva.

### 3.3 Política de retención (paso 9)
**Propuesta de reglas simples:**
- Toda imagen sin descargas en los últimos **12 meses** se marca como "candidata a archivo".
- El Responsable de Imágenes revisa y decide: archivar (dejarla disponible pero fuera del catálogo activo) o eliminar.
- Las imágenes asociadas a un curso activo nunca se archivan mientras el curso siga vigente.

### 3.4 Metadatos mínimos de trazabilidad
Se propone que cada imagen publicada guarde, como mínimo, estos metadatos (esto es la base real de la "trazabilidad" que promete el documento):

| Campo | Ejemplo |
|---|---|
| Solicitante | Nombre del docente/estudiante |
| Curso/Proyecto asociado | "Bases de Datos II - 2026-II" |
| Fecha de creación/actualización | 2026-07-23 |
| Resultado del último escaneo de seguridad | 0 críticas, 2 medias |
| Resultado del escaneo de licencias | Aprobado / Requiere revisión |
| Responsable que aprobó | Nombre |
| Firma digital (hash) | sha256:... |

---

## 4. Gobernanza de licencias de software

### 4.1 Por qué importa
El proyecto tiene dos versiones: **Académica** y **Empresarial**. Lo que es legalmente aceptable en un contexto académico (uso educativo, sin fines de lucro) puede no serlo en un contexto empresarial (uso comercial). Ejemplo: una librería con licencia **GPL** obliga a que cualquier software que la use también sea de código abierto ("efecto copyleft") — esto es inaceptable si una empresa quiere vender un producto cerrado que la incluya.

### 4.2 Tipos de licencia que el sistema debería reconocer

| Tipo | Ejemplos | Riesgo en contexto empresarial |
|---|---|---|
| Permisivas | MIT, Apache 2.0, BSD | Bajo — casi sin restricciones |
| Copyleft débil | LGPL, MPL | Medio — restricciones parciales |
| Copyleft fuerte | GPL, AGPL | Alto — puede forzar apertura del código propio |
| Propietarias/comerciales | Licencias pagadas | Alto — requieren pago o límite de instalaciones |

### 4.3 Propuesta de gobernanza
1. **Escaneo automático de licencias** integrado al mismo pipeline que corre Trivy (herramientas como **Trivy** en su modo de detección de licencias, o **FOSSA**/**Syft + Grype**, todas con opciones open source).
2. **Matriz de políticas por versión del proyecto:**
   - Versión Académica: se permiten todas las licencias open source (incluyendo GPL), ya que no hay fines comerciales.
   - Versión Empresarial: se **bloquean automáticamente** imágenes con licencias copyleft fuerte (GPL/AGPL) salvo aprobación explícita del área legal/administrador.
3. **Registro del resultado** como parte de los metadatos de trazabilidad.

### 4.4 Rol responsable
Se propone que esta responsabilidad recaiga sobre el mismo **Responsable de Imágenes** definido en el documento base, ampliando su función de "solo seguridad técnica" a "seguridad técnica + cumplimiento de licencias".

---

## 5. Riesgos de no implementar estas mejoras

- **Sin re-escaneo periódico:** una imagen puede seguir usándose durante meses con una vulnerabilidad crítica ya conocida públicamente, exponiendo tanto al laboratorio universitario como a la versión empresarial.
- **Sin gobernanza de licencias:** riesgo legal real si el proyecto evoluciona a la Fase 2 (Empresa) y se descubre, ya en producción, que se está distribuyendo software con una licencia incompatible.
- **Sin política de retención:** el catálogo de Harbor crece indefinidamente, aumentando costos de almacenamiento y dificultando encontrar la imagen "oficial" vigente entre muchas versiones obsoletas.

---

## 6. Resumen de propuestas

| # | Propuesta | Sección del doc. base que mejora |
|---|---|---|
| 1 | Gestor de secretos (Vault) | Arquitectura Técnica |
| 2 | Criterio K3s (Fase 1) vs Talos (Fase 2) | Arquitectura Técnica |
| 3 | Observabilidad (Prometheus/Grafana/Loki) | Arquitectura Técnica |
| 4 | Re-escaneo periódico de imágenes publicadas | Gestión de Imágenes |
| 5 | Escaneo y política de licencias de software | Gestión de Imágenes |
| 6 | Política de retención/deprecación | Gestión de Imágenes |
| 7 | Tabla de metadatos mínimos de trazabilidad | Gestión de Imágenes |

---

## 7. Conclusión

La propuesta de arquitectura y gestión de imágenes del documento base es un buen punto de partida técnico, pero trata la seguridad y la trazabilidad como eventos que ocurren una sola vez (al crear la imagen), en vez de como procesos continuos. Además, no contempla la dimensión legal del software (licencias), que se vuelve crítica en el momento en que el proyecto pasa de un contexto académico a uno empresarial. Las mejoras propuestas aquí buscan cerrar ambos vacíos sin rediseñar la arquitectura general, que en su base es coherente y usa herramientas estándar de la industria.
