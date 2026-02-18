# 🎓 Seminario: De Operador a Orquestador — Multiagentes

## Presentación
👉 [Ver presentación](https://scarlettdetekelala.github.io/seminario-multi-agentes/presentacion.html)

## El Reto
Crear un **plan de estudio personalizado** usando 3 agentes corriendo **en paralelo**, cada uno en su propio workspace de Google Antigravity.

### Arquitectura Multi-Agente

```
         ┌─────────────────┐
         │   TÚ (Orquestador)   │
         └────────┬────────┘
                  │ Lanza los 3 en paralelo
         ┌────────┼────────┐
         ▼        ▼        ▼
   ┌──────────┐ ┌──────────┐ ┌──────────┐
   │Workspace 1│ │Workspace 2│ │Workspace 3│
   │🔍 Invest. │ │📊 Analista│ │📋 Diseñad.│
   │mercado    │ │gaps      │ │plan+cursos│
   └─────┬────┘ └─────┬────┘ └─────┬────┘
         │            │            │
         ▼            ▼            ▼
   investigacion.md  analisis-gaps.md  plan-estudio.md
         │            │            │
         └────────┬───┘────────────┘
                  ▼
         ┌──────────────┐
         │ 🧠 Integrador │ ← Combina los 3 resultados
         └──────┬───────┘
                ▼
          plan-final.md
```

**Esto NO es encadenar prompts** — son agentes independientes trabajando en paralelo, cada uno en su propio contexto. Tú eres el orquestador que revisa, redirige y combina.

## Setup

1. Descargar [Google Antigravity](https://antigravity.google)
2. Abrir **Agent Manager** (no Editor)
3. Clonar este repo:
   ```bash
   git clone https://github.com/scarlettdetekelala/seminario-multi-agentes.git
   ```
4. Editar `mi-contexto.md` con TU información real

## Paso a Paso

1. Crear 3 workspaces en Agent Manager
2. Copiar `mi-contexto.md` a cada workspace
3. Lanzar los 3 agentes **al mismo tiempo** con los prompts de `prompts/`
4. Monitorear en **Inbox** → aprobar acciones, dar feedback
5. Cuando terminen: abrir un 4° agente con el prompt integrador
6. Resultado: `plan-final.md` — plan personalizado con mercado + gaps + recursos

## Archivos

```
📁 prompts/
   agente-1-investigador.md   → Mercado laboral + tendencias
   agente-2-analista.md       → Fortalezas y gaps
   agente-3-disenador.md      → Cursos y recursos
   agente-4-integrador.md     → Combina los 3 resultados
📁 ejemplo/                   → Resultado completo de ejemplo
📁 resultados/                → Aquí guardan sus resultados
📄 mi-contexto.md             → Editar con TU info
📄 presentacion.html          → Slides del seminario
```

## ¿Por qué es multi-agente y no solo "prompts chained"?

| Prompts encadenados | Multi-agente real |
|---|---|
| 1 chat, 1 contexto | 3 workspaces independientes |
| Secuencial (uno espera al otro) | **Paralelo** (los 3 corren al mismo tiempo) |
| El prompt 2 depende del resultado del 1 | Cada agente trabaja con el mismo input pero diferente enfoque |
| Si uno falla, todo se detiene | Si uno falla, los otros siguen |
| Tú pegás prompts | Tú **orquestas**: revisas en Inbox, apruebas, rediriges |

## Créditos
Seminario de Complejidad · Business Cyborgs · Camilo Serna Zamora · Febrero 2026
