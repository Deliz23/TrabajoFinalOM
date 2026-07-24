# Metodología y Organización del Equipo (Modelo Spotify) - Propuestas de Mejora

**Autor:** Fabrizio
**Proyecto:** Plataforma Híbrida de Gestión de Laboratorios de Computación
**Secciones revisadas:** Enfoque Metodológico, Modelo Organizacional Ágil (Spotify), Requisitos de Conocimientos y Habilidades

---

## 1. Diagnóstico del documento base

El documento original plantea una buena estructura organizacional (Tribe, Squads, Chapters, Guilds) inspirada en el modelo Spotify, y define bien qué nivel de conocimiento se espera de cada rol en cada fase del proyecto. Sin embargo, tiene tres vacíos importantes que se notan apenas se piensa en cómo se usaría esto en la práctica, semana a semana:

1. **No define cómo se trabaja en el día a día.** Se dice qué estructura tiene el equipo, pero no cómo se organiza el trabajo dentro de esa estructura (no hay sprints, ceremonias, ni forma de medir avance).
2. **Los Guilds y la coordinación entre Squads quedan solo mencionados, no definidos.** Aparecen como nombres en el organigrama, pero no como algo que realmente vaya a funcionar.
3. **Los requisitos de los estudiantes son solo técnicos.** No se considera nada de habilidades blandas ni cómo se integra alguien nuevo a mitad de proyecto.

Las siguientes secciones desarrollan propuestas concretas para cerrar estos tres vacíos.

---

## 2. Enfoque Metodológico

**Lo que rescato:** el modelo Spotify tiene sentido para un equipo como el nuestro, porque está pensado para squads chicos que se mueven rápido sin depender de mucha jerarquía. También está bien plantear el proyecto en dos etapas (universidad → empresa), para no enfrentar de golpe el nivel más exigente.

**El vacío:** no hay ninguna cadencia de trabajo definida. Sin eso, cada Squad avanza a su propio ritmo y sin forma de saber si el proyecto va bien o mal hasta que ya es tarde.

**Propuesta — cadencia de trabajo:**

| Momento | Qué se hace |
|---|---|
| Cada 2 semanas (sprint) | Se cierra un ciclo de trabajo |
| Inicio del sprint | El squad elige 3-4 tareas concretas de su backlog |
| Durante la semana | Avances rápidos por el chat del equipo (no hace falta reunión presencial) |
| Fin del sprint | Se revisa qué se logró y qué falta, y se planea el siguiente |

No requiere herramientas complicadas, solo que el equipo respete esta cadencia para que el proyecto avance de forma predecible.

---

## 3. Modelo Organizacional Ágil (Spotify)

**Lo que rescato:** la evolución de los Squads del Proyecto 1 al Proyecto 2 está bien pensada (por ejemplo, el squad de imágenes pasa de manejar solo Docker a incluir seguridad avanzada).

**El vacío:** no se explica cómo se comunican los Squads entre sí cuando uno depende de otro (por ejemplo, Frontend necesitando algo que primero debe entregar Core Platform), y los Guilds solo aparecen nombrados, sin decir qué harían.

**Propuesta:**

| Vacío | Propuesta |
|---|---|
| Squads no se coordinan entre sí | Reunión semanal corta: un representante de cada Squad cuenta en qué está y si necesita algo de otro |
| Guilds sin definir | 3 Guilds concretos: Seguridad, Infraestructura/DevOps, Documentación — reunión mensual, participación voluntaria |
| Nadie organiza al Squad por dentro | Rol rotativo (cambia cada sprint) que organiza reuniones y anota pendientes — no es un jefe |

---

## 4. Requisitos de Conocimientos y Habilidades

**Lo que rescato:** pedir un rol de Seguridad desde el primer proyecto es un acierto poco común en proyectos universitarios.

**El vacío:** la tabla original solo pide conocimientos técnicos. No menciona habilidades blandas, que en un modelo con tanta autonomía como Spotify son igual de importantes, y tampoco hay forma de que un estudiante sepa si está listo para su rol, ni un plan para quien se una después de iniciado el proyecto.

**Propuesta — habilidades blandas por rol:**

| Rol | Habilidad blanda clave |
|---|---|
| Tech Lead | Comunicar bien sus decisiones y priorizar |
| DevOps | Mantener la calma cuando algo falla en producción |
| UX/UI | Saber recibir feedback sin tomarlo como algo personal |
| Backend / Security | Documentar de forma clara para que otros entiendan su trabajo |

**Otras propuestas:**
- Autoevaluación simple (escala 1-5) antes de asignarse a un rol, para calibrar si necesita apoyo extra.
- Guía de onboarding de 1 semana para estudiantes que se integren después del inicio, con documentación mínima y un compañero del mismo squad como guía.

---

## 5. Riesgos de no implementar estas mejoras

- **Sin cadencia definida:** el equipo puede avanzar sin sincronización, y recién notar el atraso cerca de la entrega final, cuando ya es tarde para corregir.
- **Sin coordinación entre Squads:** un equipo puede quedar bloqueado esperando algo de otro sin que nadie se entere a tiempo, atrasando toda la cadena de trabajo.
- **Sin habilidades blandas consideradas:** un estudiante técnicamente capaz pero que no comunica bien puede generar fricciones dentro de su Squad, afectando el ritmo de todo el equipo.
- **Sin plan de onboarding:** un estudiante nuevo puede tardar semanas en ser productivo, simplemente por no saber por dónde empezar.

---

## 6. Resumen de propuestas

| # | Propuesta | Sección que mejora |
|---|---|---|
| 1 | Sprints de 2 semanas con cadencia fija | Enfoque Metodológico |
| 2 | Reunión semanal entre Squads | Modelo Organizacional |
| 3 | 3 Guilds concretos y definidos | Modelo Organizacional |
| 4 | Rol rotativo de organizador por Squad | Modelo Organizacional |
| 5 | Habilidades blandas en la tabla de roles | Requisitos de Habilidades |
| 6 | Autoevaluación antes de asignar rol | Requisitos de Habilidades |
| 7 | Guía de onboarding de 1 semana | Requisitos de Habilidades |
