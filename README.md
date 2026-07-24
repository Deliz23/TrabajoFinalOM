# Plataforma Híbrida de Gestión de Laboratorios de Computación

**Proyecto Académico-Empresarial**  
**Carrera de Sistemas / Ingeniería de Software**  
**Universidad [Nombre de la Universidad]**  
**Versión:** 1.0 (Propuesta)  
**Fecha:** Julio 2026

---

## 📋 Tabla de Contenidos

- [Introducción](#introducción)
- [Problemática Común](#problemática-común)
- [Objetivos](#objetivos)
- [Justificación y Beneficios](#justificación-y-beneficios)
- [Enfoque Metodológico](#enfoque-metodológico)
- [Modelo Organizacional Ágil (Spotify Adaptado)](#modelo-organizacional-ágil-spotify-adaptado)
- [Requisitos de Conocimientos y Habilidades](#requisitos-de-conocimientos-y-habilidades)
- [Arquitectura Técnica Propuesta](#arquitectura-técnica-propuesta)
- [Gestión de Imágenes y Trazabilidad](#gestión-de-imágenes-y-trazabilidad)
- [Fases de Implementación](#fases-de-implementación)
- [Conclusiones y Recomendaciones](#conclusiones-y-recomendaciones)
- [Anexos](#anexos)

---

## Introducción

Este proyecto propone el desarrollo de una **Plataforma Híbrida** para la gestión integral de laboratorios de computación, aplicable tanto en entornos universitarios como en empresas de software.

La solución combina gestión de hardware (computadoras, servidores, impresoras), usuarios, proyectos/cursos, repositorios de código (GitLab) y un catálogo centralizado de imágenes de contenedores (Docker), garantizando **estandarización, trazabilidad y reproducibilidad** de entornos.

```diff
**[Comentario Flor:]** Se recomienda ampliar el contexto inicial describiendo con mayor detalle las dificultades actuales en la gestión de laboratorios y especificar los actores involucrados (estudiantes, docentes, administradores y personal de soporte). Esto permitirá comprender mejor el alcance y la necesidad de la plataforma.
```
---

## Problemática Común

Los laboratorios universitarios y las empresas de software enfrentan problemas similares:

- Gestión fragmentada de recursos físicos y digitales.
- Pérdida significativa de tiempo en instalaciones y configuraciones manuales.
- Entornos no estandarizados que generan inconsistencias ("funciona en mi máquina").
- Falta de trazabilidad del software e imágenes utilizadas.
- Dificultad para replicar entornos entre laboratorio y computadoras personales de estudiantes/desarrolladores.
- Escalabilidad limitada al pasar de academia a industria.

**En el ámbito universitario** se busca especialmente que los alumnos **no pierdan tiempo** en instalaciones y que puedan llevarse las mismas imágenes oficiales a sus computadoras personales para practicar fuera del laboratorio.

```diff
**[Comentario Flor:]** Se sugiere complementar la problemática con ejemplos concretos de situaciones frecuentes, como conflictos en la reserva de laboratorios, falta de control sobre las imágenes Docker o dificultades en la administración de software. Asimismo, sería conveniente mencionar la importancia de la trazabilidad y la gobernanza para garantizar un adecuado seguimiento de los recursos tecnológicos.
```
---

## Objetivos

### Objetivo General
Desarrollar una plataforma híbrida (local + nube) que permita la gestión estandarizada, segura y trazable de laboratorios de computación en contextos académicos y empresariales.

### Objetivos Específicos
- Implementar catálogo centralizado de imágenes de contenedores con procesos automatizados.
- Gestionar usuarios, proyectos/cursos y recursos físicos de forma eficiente.
- Garantizar trazabilidad completa del software utilizado.
- Permitir a los estudiantes descargar y ejecutar localmente las imágenes del laboratorio.
- Crear dos versiones: Académica y Empresarial (con estándares superiores).
- Formar estudiantes bajo metodologías ágiles reales (Modelo Spotify).

```diff
**[Comentario Flor:]** Se propone incorporar objetivos específicos relacionados con la auditoría de actividades, el control de versiones de imágenes Docker y la administración de licencias de software, con el fin de fortalecer la gestión y la seguridad de la plataforma.
```
---

## Justificación y Beneficios

**Beneficios Universitarios:**
- Ahorro de tiempo para estudiantes y administradores.
- Entornos idénticos y reproducibles.
- Mayor calidad de proyectos y prácticas.
- Trazabilidad académica.

**Beneficios Empresariales:**
- Plataforma lista para entornos productivos.
- Estudiantes formados con estándares profesionales.
- Reducción de riesgos operativos.

```diff
**[Comentario Flor:]** Se recomienda ampliar los beneficios del proyecto considerando aspectos como la trazabilidad de las operaciones, el fortalecimiento del control administrativo, la escalabilidad de la plataforma y la optimización de la gestión de recursos tecnológicos mediante procesos estandarizados.
```
---

## Enfoque Metodológico

El proyecto se desarrollará utilizando el **Modelo Spotify** adaptado al contexto universitario:

- **Tribe:** Platform Lab
- **Squads** multidisciplinarios (5-9 miembros)
- **Chapters** liderados por profesores con experiencia en industria
- **Guilds** temáticos

Se ejecutarán dos proyectos secuenciales:
1. **Proyecto Universitario** (Fase 1)
2. **Proyecto Empresa** (Fase 2)

```diff
**[Fabrizio - Comentario]:** A favor del modelo Spotify porque encaja con equipos pequeños y multidisciplinarios como los nuestros. Observación: no se define la cadencia de trabajo (sprints, ceremonias) ni cómo se sincronizan los Squads entre sí cuando hay dependencias cruzadas. Propuesta: fijar sprints de 2 semanas con ceremonias mínimas (Planning, Daily async, Review, Retro) y una reunión semanal tipo "Scrum of Scrums" entre representantes de cada Squad.
```
---

## Modelo Organizacional Ágil (Spotify Adaptado)

### Squads Principales

**Proyecto 1 - Universitario**
- Squad Core Platform
- Squad Image & Container Management
- Squad Hardware & Lab Operations
- Squad Frontend & User Experience

**Proyecto 2 - Empresa** (evolución)
- Squad Core Enterprise Platform
- Squad Advanced Image & Security
- Squad Hardware Fleet & Hybrid Operations
- Squad Enterprise Experience & Analytics
- Squad Integration & Ecosystem

Los **Chapters** serán liderados por profesores con mínimo 5 años de experiencia industrial.

```diff
**[Fabrizio - Comentario]:** A favor de la diferenciación clara de Squads entre Proyecto 1 y 2. Observación: se mencionan Guilds "temáticos" pero no se define qué Guilds existen ni cómo funcionan en la práctica. Propuesta: definir desde el inicio al menos 3 Guilds concretos (Seguridad, DevOps/Infraestructura, Documentación), con reunión mensual y participación voluntaria, además de un rol rotativo de "Agile Facilitator" dentro de cada Squad (no jefe, sino quien organiza las ceremonias).
```

---

## Requisitos de Conocimientos y Habilidades

### Cuadro Comparativo (Resumen)

| Rol                          | Proyecto 1 (Nivel)     | Tiempo Mín. Práctica | Proyecto 2 (Nivel)      | Tiempo Mín. Práctica |
|-----------------------------|------------------------|----------------------|-------------------------|----------------------|
| Tech Lead / Arquitecto      | Avanzado              | 2 semestres         | Senior                 | 4 semestres         |
| Backend Developer           | Intermedio-Avanzado   | 2 semestres         | Avanzado               | 3-4 semestres       |
| DevOps / Platform Engineer  | Intermedio            | 1-2 semestres       | Senior                 | 3-4 semestres       |
| Security Engineer           | Básico-Intermedio     | 1 semestre          | Avanzado               | 2-3 semestres       |
| UX/UI Designer              | Intermedio            | 1-2 semestres       | Avanzado               | 2-3 semestres       |

**Requisitos Generales:**
- Proyecto 1: 3er-4to semestre, promedio mínimo 14, portafolio GitHub.
- Proyecto 2: Haber participado en Proyecto 1 (preferible), conocimientos avanzados en Kubernetes, GitOps y Seguridad.
```diff
**[Fabrizio - Comentario]:** A favor de exigir Security Engineer desde el Proyecto 1, algo poco común y valioso. Observación: la tabla solo lista habilidades técnicas, sin habilidades blandas (comunicación, trabajo en equipo), críticas en un modelo con alta autonomía como Spotify. Propuesta: agregar columna de habilidades blandas por rol, un checklist de autoevaluación (1-5) antes de asignar Squad, y un plan de onboarding de 1 semana para estudiantes que se integren después del inicio.
```
---

## Arquitectura Técnica Propuesta

- **Modelo Híbrido**: On-premise (Proxmox + Kubernetes) + Nube
```diff
**Comentario-Joseph:** no se especifica qué parte va on-premise y qué parte va en nube. Propuesta: aclarar que los servidores de cómputo intensivo (K8s) y las imágenes sensibles quedan on-premise, mientras que backups y colaboración externa (GitLab) pueden ir en nube.
```
- **Componentes principales**:
  - GitLab (código y CI/CD)
  - Harbor (Registry de imágenes)
  - Keycloak (Identity & Access)
  - PostgreSQL + MinIO

```diff
**Comentario-Joseph:** el stack es coherente y usa herramientas open source reales, lo cual reduce costos de licenciamiento. Observación: falta un componente de gestión de secretos (contraseñas, tokens, llaves de firma) sin esto, las credenciales quedarían dispersas. Propuesta: agregar HashiCorp Vault o el Secrets Manager nativo de Kubernetes.
```
- **Infraestructura**: Proxmox VE, Kubernetes (K3s/Talos), Ansible + Terraform
  
```diff
**Comentario-Joseph:** no se justifica la elección entre K3s y Talos, son alternativas distintas (K3s es más liviano y fácil de mantener; Talos es más seguro pero con curva de aprendizaje mayor). Propuesta: definir criterio de elección según el nivel del proyecto (K3s para Fase 1 Universitaria, Talos para Fase 2 Empresa, por mayor exigencia de seguridad).
```

---

## Gestión de Imágenes y Trazabilidad

**Flujo Principal:**
1. Solicitud de imagen
2. Búsqueda automática en Harbor
3. Creación/Importación + Escaneo (Trivy)
4. Firma digital y aprobación
5. Publicación con metadatos
6. Descarga segura por estudiantes
7. Actualizaciones controladas

```diff
**Comentario-Joseph:** el flujo cubre bien el ciclo de vida de creación y publicación de una imagen. Observación importante: el flujo escanea la imagen solo UNA VEZ, al crearla no contempla qué pasa si se descubre una vulnerabilidad nueva DESPUÉS de que la imagen ya fue publicada y está en uso (esto es muy común, las vulnerabilidades se descubren constantemente). Propuesta: agregar un paso 8 de "Re-escaneo periódico" de imágenes ya publicadas.

**Comentario-Joseph:** no se menciona la gestión de licencias de software dentro de las imágenes, solo seguridad (vulnerabilidades). Propuesta: agregar un escaneo de licencias en el mismo paso 3, para detectar si alguna librería incluida tiene una licencia incompatible con el uso que se le dará (académico vs. comercial en Fase 2 Empresa).

**Comentario-Joseph:** no se define qué pasa con imágenes obsoletas o que ya no se usan el catálogo puede crecer indefinidamente. Propuesta: política de retención/deprecación (ej: archivar imágenes sin uso en 12 meses).

Esto garantiza **estandarización y trazabilidad completa**.
```
---

## Fases de Implementación

1. Análisis y Diseño (1 mes)
2. Desarrollo Proyecto Universitario (4-6 meses)
3. Evolución a Proyecto Empresa (5-7 meses)
4. Piloto y Puesta en Producción
5. Mejora Continua

```diff
- [Comentario de Usiel - Responsable de Fases de Implementación]&#58; 
- 1. A favor: La división del proyecto en fases permite tener una visión general del proceso de desarrollo y facilita la planificación del trabajo.

- 2. Observación/Riesgo: No se especifican las actividades, entregables ni responsables de cada fase, lo que puede generar confusión durante la ejecución del proyecto.

- 3. Observación/Riesgo: Tampoco se definen criterios que permitan saber cuándo una fase ha sido completada correctamente antes de pasar a la siguiente.

- 4. Mejora propuesta: Agregar un cronograma donde cada fase incluya sus actividades principales, responsables, entregables y criterios de finalización para mejorar el seguimiento del proyecto.
```
---

## Conclusiones y Recomendaciones

Esta plataforma representa una oportunidad estratégica para modernizar los laboratorios de la universidad, elevar la calidad formativa y generar un activo tecnológico de alto valor transferable a la industria.

**Recomendaciones:**
- Aprobar como proyecto inter-cátedra.
- Asignar presupuesto para infraestructura base.
- Formalizar participación de profesores como Chapter Leads.

---
```diff
- [Comentario de Usiel - Responsable de Conclusiones y Recomendaciones]&#58; 
- 1. A favor: Las conclusiones resumen adecuadamente el propósito general del proyecto y destacan su impacto tanto en el ámbito académico como empresarial.

- 2. Observación/Riesgo: No se mencionan posibles desafíos o riesgos que podrían presentarse durante la implementación de la plataforma.

- 3. Observación/Riesgo: Las recomendaciones son útiles, pero podrían ser insuficientes para garantizar la sostenibilidad del proyecto a largo plazo.

- 4. Mejora propuesta: Incorporar recomendaciones relacionadas con mantenimiento periódico, capacitación continua de los usuarios, monitoreo del sistema e indicadores que permitan evaluar el éxito del proyecto después de su implementación.
```

## Anexos

### Anexo 1: Tabla Detallada de Roles y Habilidades

*(Ver documento complementario `roles-habilidades.md`)*

### Anexo 2: Diagrama de Arquitectura (C4)

*(Se incluirán diagramas en formato PlantUML o Draw.io dentro de la carpeta `/docs/architecture`)*

### Anexo 3: Backlog Inicial de Épicas

*(Ver carpeta `/backlog`)*

### Anexo 4: Plan de Dedicación Semanal por Squad

*(Ver documento `plan-dedicacion.md`)*

### Anexo 5: Estimación de Costos Iniciales

*(Ver documento `costos.md`)*

---
```diff
- [Comentario de Usiel - Responsable de Anexos]&#58; 
- 1. A favor: Los anexos permiten organizar la documentación complementaria sin sobrecargar el documento principal.

- 2. Observación/Riesgo: Algunos documentos mencionados en los anexos aún no existen dentro del repositorio, por lo que la información queda incompleta.

- 3. Observación/Riesgo: No se describe el contenido esperado de cada anexo ni su relación con el desarrollo del proyecto.

- 4. Mejora propuesta: Incorporar los documentos faltantes y agregar una breve descripción del objetivo de cada anexo para facilitar su consulta y comprensión.
```
## Cómo Contribuir

1. Leer el [Code of Conduct](CODE_OF_CONDUCT.md)
2. Seguir las [guías de contribución](CONTRIBUTING.md)
3. Crear issues y pull requests

---

**Licencia:** MIT  
**Estado del Proyecto:** Propuesta Inicial (En fase de aprobación)

---

*Documento preparado para repositorio GitHub. Puedes copiar todo este contenido directamente en un archivo `README.md`.*
