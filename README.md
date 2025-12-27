# CC Partner

Skills para construir software con IA usando Claude Code - desde cero hasta produccion.

## Instalacion

### 1. Agregar el marketplace (solo una vez)

```bash
claude plugin marketplace add https://github.com/adriestevezdev/cc-partner-marketplace
```

### 2. Instalar el plugin

```bash
claude plugin install cc-partner@cc-partner-marketplace
```

### 3. Verificar instalacion

```bash
claude -p "que skills de cc-partner tengo?"
```

---

## Skills disponibles

| Skill | Comando | Descripcion |
|-------|---------|-------------|
| Empezar | `/cc-partner:empezar` | Inicia un proyecto desde cero con guia paso a paso |
| Brainstorm | `/cc-partner:brainstorm` | Disena features antes de implementar |
| Planificar | `/cc-partner:planificar` | Divide tareas complejas en subtareas |
| Ejecutar | `/cc-partner:ejecutar` | Ejecuta tareas con subagentes |

---

## Casos de uso

### `/cc-partner:empezar` - Iniciar un proyecto

Perfecto cuando no sabes por donde empezar. El skill te guia con preguntas:

```
Tu: /cc-partner:empezar

CC-Partner: Que quieres construir? Describelo en una frase.

Tu: Una app para guardar recetas de cocina

CC-Partner: Que tipo de proyecto es?
1. Aplicacion web
2. Solo API/backend
3. Script o CLI
4. Otro

Tu: 1

CC-Partner: Tienes preferencia de tecnologias o te recomiendo?
1. Recomiendame (ideal si estas empezando)
2. Tengo preferencias

Tu: 1

CC-Partner: Para una app de recetas te recomiendo:
- Frontend: React + Vite
- Backend: Node.js + Express
- Base de datos: SQLite

Te parece bien?

Tu: Si

CC-Partner: Creando estructura del proyecto...
[Genera carpetas, archivos, y plan de implementacion]
```

---

### `/cc-partner:brainstorm` - Disenar una feature

Usa esto antes de agregar funcionalidad. Explora opciones antes de codear:

```
Tu: /cc-partner:brainstorm
Quiero agregar sistema de favoritos

CC-Partner: Cuando un usuario marca favorito, que deberia pasar?
1. Solo guardarla en una lista
2. Guardarla y organizar en colecciones
3. Guardarla con notas personales

Tu: 1

CC-Partner: Veo dos enfoques:

1. Tabla de relacion (Recomendado)
   - Nueva tabla: user_favorites
   - Pro: Simple y escalable

2. Array en el modelo User
   - Pro: Menos tablas
   - Con: Dificil de paginar

Cual prefieres?

Tu: 1

CC-Partner: [Presenta diseno en secciones para validar]
```

---

### `/cc-partner:planificar` - Dividir tareas

Cuando tienes algo complejo, dividelo antes de empezar:

```
Tu: /cc-partner:planificar
Quiero agregar autenticacion completa

CC-Partner: Analizando tu proyecto...

Plan: Sistema de Autenticacion

Fase 1: Base de datos
| Tarea | Dependencias |
|-------|--------------|
| Crear modelo User | Ninguna |
| Crear modelo Session | User |

Fase 2: Backend
| Tarea | Dependencias |
|-------|--------------|
| API registro | User |
| API login | User, Session |
| Middleware auth | Session |

Fase 3: Frontend
| Tarea | Dependencias |
|-------|--------------|
| Form registro | API registro |
| Form login | API login |

Quieres que guarde el plan?
```

---

### `/cc-partner:ejecutar` - Ejecutar el plan

Una vez tienes un plan, ejecutalo con subagentes:

```
Tu: /cc-partner:ejecutar

CC-Partner: Leyendo plan en docs/plan.md...

Encontre 6 tareas. Ejecutando:

Tarea 1: Crear modelo User
[Despacha subagente]
Subagente: Completado. Tests pasan.

Tarea 2: API registro
[Despacha subagente]
Subagente: Tengo una pregunta - que campos necesita el registro?

CC-Partner: Solo email y password

Subagente: Entendido. Implementando...
Subagente: Completado. Tests pasan.

[Continua con cada tarea...]
```

---

## Para quien es

**Principiantes:**
- Guia paso a paso
- Explicaciones claras
- Recomendaciones de tecnologias
- No necesitas saber que stack usar

**Desarrolladores:**
- Workflows profesionales
- Divide y conquista con subagentes
- Automatiza tareas repetitivas
- Best practices integradas

---

## Flujo recomendado

```
/cc-partner:empezar     → Crear proyecto nuevo
        ↓
/cc-partner:brainstorm  → Disenar cada feature
        ↓
/cc-partner:planificar  → Dividir en tareas
        ↓
/cc-partner:ejecutar    → Implementar con subagentes
```

---

## Requisitos

- [Claude Code](https://claude.com/code) instalado
- Cuenta de Claude activa

---

## Contribuir

1. Fork este repositorio
2. Crea tu feature branch
3. Haz tus cambios
4. Crea un Pull Request

---

## Licencia

MIT
