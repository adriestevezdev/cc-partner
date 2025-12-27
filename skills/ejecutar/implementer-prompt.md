# Prompt para Subagente Implementador

Usa esta plantilla cuando despaches un subagente implementador.

```
Task tool (general-purpose):
  description: "Implementar Tarea N: [nombre de la tarea]"
  prompt: |
    Estas implementando la Tarea N: [nombre de la tarea]

    ## Descripcion de la Tarea

    [TEXTO COMPLETO de la tarea del plan - pegarlo aqui, no hacer que el subagente lea el archivo]

    ## Contexto

    [Donde encaja esta tarea en el proyecto, dependencias, contexto arquitectural]

    ## Antes de Empezar

    Si tienes preguntas sobre:
    - Los requisitos o criterios de aceptacion
    - El enfoque o estrategia de implementacion
    - Dependencias o suposiciones
    - Cualquier cosa poco clara en la descripcion

    **Pregunta ahora.** Plantea cualquier duda antes de empezar a trabajar.

    ## Tu Trabajo

    Una vez que tengas claros los requisitos:
    1. Implementar exactamente lo que especifica la tarea
    2. Escribir tests (siguiendo TDD si la tarea lo indica)
    3. Verificar que la implementacion funciona
    4. Hacer commit de tu trabajo
    5. Auto-revision (ver abajo)
    6. Reportar

    Trabajar desde: [directorio]

    **Mientras trabajas:** Si encuentras algo inesperado o poco claro, **pregunta**.
    Siempre esta bien pausar y clarificar. No adivines ni hagas suposiciones.

    ## Antes de Reportar: Auto-Revision

    Revisa tu trabajo con ojos frescos. Preguntate:

    **Completitud:**
    - Implemente todo lo que pide la spec?
    - Me salte algun requisito?
    - Hay casos edge que no maneje?

    **Calidad:**
    - Es mi mejor trabajo?
    - Los nombres son claros y precisos (reflejan lo que hacen, no como funcionan)?
    - El codigo es limpio y mantenible?

    **Disciplina:**
    - Evite sobre-construir (YAGNI)?
    - Solo construi lo que se pidio?
    - Segui los patrones existentes del codebase?

    **Testing:**
    - Los tests verifican comportamiento real (no solo mockean)?
    - Segui TDD si era requerido?
    - Los tests son comprehensivos?

    Si encuentras problemas en la auto-revision, arreglalos ahora antes de reportar.

    ## Formato del Reporte

    Cuando termines, reporta:
    - Que implementaste
    - Que testeaste y resultados
    - Archivos cambiados
    - Hallazgos de auto-revision (si los hay)
    - Cualquier problema o preocupacion
```
