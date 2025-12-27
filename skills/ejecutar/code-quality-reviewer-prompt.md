# Prompt para Revisor de Calidad de Codigo

Usa esta plantilla cuando despaches un subagente revisor de calidad.

**Proposito:** Verificar que la implementacion esta bien construida (limpia, testeada, mantenible)

**Solo despachar despues de que la revision de spec pase.**

```
Task tool (superpowers:code-reviewer):
  description: "Revisar calidad de Tarea N"
  prompt: |
    Estas revisando la calidad del codigo de una implementacion.

    ## Que se Implemento

    [Del reporte del implementador]

    ## Contexto

    Tarea N del plan: [nombre del archivo del plan]
    Commit base (antes de tarea): [SHA]
    Commit actual: [SHA]

    ## Tu Trabajo

    Revisa el codigo buscando:

    **Legibilidad:**
    - Los nombres son claros y descriptivos?
    - El codigo es facil de seguir?
    - Hay comentarios donde se necesitan (y solo donde se necesitan)?

    **Mantenibilidad:**
    - El codigo sigue los patrones del proyecto?
    - Esta bien estructurado?
    - Seria facil modificar en el futuro?

    **Testing:**
    - Los tests son comprehensivos?
    - Testean comportamiento real, no mocks?
    - Cubren casos edge?

    **Mejores practicas:**
    - DRY (no hay codigo duplicado)?
    - YAGNI (no hay sobre-ingenieria)?
    - Manejo de errores apropiado?
    - Sin vulnerabilidades de seguridad obvias?

    ## Formato del Reporte

    Reporta:

    **Fortalezas:**
    - [Lo que esta bien hecho]

    **Problemas:**
    - Critico: [Debe arreglarse antes de merge]
    - Importante: [Deberia arreglarse]
    - Menor: [Nice to have]

    **Veredicto:**
    - ✅ Aprobado
    - ❌ Requiere cambios: [lista de lo que debe arreglarse]
```

## Alternativa: Usar agente code-reviewer

Si tienes acceso al agente `superpowers:code-reviewer`, puedes usarlo directamente:

```
Task tool (superpowers:code-reviewer):
  WHAT_WAS_IMPLEMENTED: [del reporte del implementador]
  PLAN_OR_REQUIREMENTS: Tarea N del [archivo-plan]
  BASE_SHA: [commit antes de la tarea]
  HEAD_SHA: [commit actual]
  DESCRIPTION: [resumen de la tarea]
```
