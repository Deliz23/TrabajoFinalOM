# Metodología y Organización del Equipo (Modelo Spotify) - Propuestas de Mejora

**Autor:** Fabrizio
**Proyecto:** Plataforma Híbrida de Gestión de Laboratorios de Computación

Revisé tres partes del documento base: el Enfoque Metodológico, el Modelo Organizacional Ágil (Spotify) y los Requisitos de Conocimientos y Habilidades. Este documento resume lo que encontré y qué cambiaría.

## Qué propone el documento original

La idea es organizar al equipo copiando el modelo que usa Spotify: hay un "Tribe" (el equipo grande, llamado Platform Lab), dividido en "Squads" de 5 a 9 personas que se encargan cada uno de una parte del proyecto. Los "Chapters" son básicamente los profesores guiando por especialidad, y los "Guilds" son espacios donde gente de distintos Squads comparte conocimiento sobre un tema en común.

También hay una tabla que dice qué nivel de conocimiento necesita cada rol (Tech Lead, Backend, DevOps, Security, UX/UI), separando lo que se pide en el proyecto de la universidad de lo que se pediría en el proyecto de empresa.

## Lo que me parece bien

Creo que elegir el modelo Spotify tiene sentido para un equipo como el nuestro, porque no somos una empresa grande y este modelo está pensado justamente para squads chicos que puedan moverse rápido sin depender de mucha jerarquía. También me gusta que se plantee el proyecto en dos etapas, primero universidad y después empresa, porque así uno no se enfrenta de golpe al nivel más exigente.

Otra cosa que rescato es que se le esté pidiendo un rol de Seguridad desde el primer proyecto. La mayoría de proyectos universitarios ni siquiera consideran seguridad como algo importante, y acá sí aparece desde el inicio.

## Lo que le falta al documento

Cuando lo leí con más detalle, noté que el documento se queda bastante en la idea general y no baja a cómo se haría en la práctica. Por ejemplo:

No dice nada sobre cómo se va a organizar el trabajo semana a semana. No hay sprints, no hay reuniones definidas, no hay nada que diga cada cuánto tiempo el equipo se junta a revisar en qué va el proyecto. Si esto no se define, cada Squad puede terminar trabajando a su ritmo y sin ninguna sincronización.

Tampoco queda claro cómo se van a comunicar los Squads entre sí. El proyecto tiene squads que dependen unos de otros (por ejemplo, el squad de Frontend seguro necesita cosas que entregue el squad de Core Platform), pero no hay ningún mecanismo pensado para esa coordinación.

Los Guilds se mencionan pero literalmente es solo la palabra "Guilds temáticos", sin decir cuáles serían ni qué harían. Tal como está, es más un nombre bonito que algo real.

Además, no hay ningún rol que se encargue de organizar al Squad por dentro. No hace falta un jefe, pero sí alguien que se asegure de que las reuniones pasen y que se anote qué falta hacer.

Sobre la tabla de habilidades, noté que solo pide cosas técnicas (saber Kubernetes, saber Docker, etc.) pero no menciona nada de habilidades blandas, que en un modelo donde cada Squad trabaja con bastante autonomía terminan siendo tan importantes como lo técnico.

Y por último, no hay ningún plan para cuando entra un estudiante nuevo a mitad del proyecto. No sabría ni por dónde empezar.

## Qué propongo

**Sobre cómo trabajar día a día:** propongo trabajar con sprints de 2 semanas. Al inicio del sprint el squad decide qué va a hacer, durante la semana se pueden dar avances rápidos aunque sea por el grupo de chat, y al final del sprint se revisa qué se logró y qué no. No hace falta que sea complicado, con que se respete la cadencia ya ayuda bastante.

**Sobre la comunicación entre squads:** una reunión corta, una vez por semana, donde un representante de cada Squad cuenta en qué está y si necesita algo de otro squad. Así se evita que un equipo se entere tarde de que estaba bloqueado esperando algo.

**Sobre quién organiza al squad:** que exista un rol rotativo (cambia cada sprint) encargado de organizar las reuniones y anotar pendientes. Rotarlo entre todos ayuda a que no recaiga siempre en la misma persona y de paso todos practican ese rol.

**Sobre los Guilds:** definir de una vez 3 Guilds concretos en vez de dejarlo en el aire. Yo propondría uno de Seguridad, uno de Infraestructura/DevOps y uno de Documentación. Que se reúnan una vez al mes y que sea voluntario participar.

**Sobre la tabla de habilidades:** agregar una columna con las habilidades blandas que se esperan de cada rol (por ejemplo, el Tech Lead necesita comunicar bien sus decisiones, el DevOps necesita manejar bien la presión). También propongo que antes de asignarse a un rol, cada estudiante se autoevalúe del 1 al 5 para saber si está realmente listo o si necesita apoyo extra.

**Sobre estudiantes nuevos:** armar una guía corta, de una semana, para que alguien que se sume después del inicio pueda ponerse al día rápido, con ayuda de algún compañero del mismo squad.

## Para exponer

Si tengo que resumir esto en pocas palabras: el modelo Spotify como está planteado es una buena idea pero le falta bajar a tierra. Mis propuestas apuntan justo a eso, a que se pueda usar desde el primer día y no se quede solo como un esquema bonito en el papel.
