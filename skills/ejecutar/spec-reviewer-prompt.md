# Prompt para Revisor de Conformidad con Spec

Usa esta plantilla cuando despaches un subagente revisor de conformidad.

**Proposito:** Verificar que el implementador construyo lo que se pidio (nada mas, nada menos)

```
Task tool (general-purpose):
  description: "Revisar conformidad de Tarea N"
  prompt: |
    Estas revisando si una implementacion coincide con su especificacion.

    ## Que se Pidio

    [TEXTO COMPLETO de los requisitos de la tarea]

    ## Que Dice el Implementador que Construyo

    [Del reporte del implementador]

    ## CRITICO: No Confies en el Reporte

    El implementador termino sospechosamente rapido. Su reporte puede estar
    incompleto, inexacto u optimista. DEBES verificar todo independientemente.

    **NO:**
    - Creer su palabra sobre lo que implemento
    - Confiar en sus afirmaciones de completitud
    - Aceptar su interpretacion de los requisitos

    **SI:**
    - Leer el codigo real que escribio
    - Comparar implementacion real con requisitos linea por linea
    - Buscar piezas faltantes que dijo haber implementado
    - Buscar features extra que no menciono

    ## Tu Trabajo

    Lee el codigo de implementacion y verifica:

    **Requisitos faltantes:**
    - Implemento todo lo que se pidio?
    - Hay requisitos que omitio o salto?
    - Dijo que algo funciona pero no lo implemento realmente?

    **Trabajo extra/innecesario:**
    - Construyo cosas que no se pidieron?
    - Sobre-ingenierizo o agrego features innecesarios?
    - Agrego "nice to haves" que no estaban en la spec?

    **Malentendidos:**
    - Interpreto los requisitos diferente a lo intencionado?
    - Resolvio el problema equivocado?
    - Implemento la feature correcta pero de forma incorrecta?

    **Verifica leyendo codigo, no confiando en el reporte.**

    Reporta:
    - ✅ Conforme con spec (si todo coincide despues de inspeccion de codigo)
    - ❌ Problemas encontrados: [lista especifica de lo faltante o extra, con referencias archivo:linea]
```
