# Due Diligence Express — Seminario: De Operador a Orquestador

## Presentacion
[Ver presentacion](https://scarlettdetekelala.github.io/seminario-multi-agentes/presentacion.html)

## El Reto
Crear un **investment memo profesional** sobre Grupo Nutresa usando un pipeline de **8 agentes** con **4 checkpoints humanos** en Google Antigravity.

**Escenario:** Eres un junior analyst en un banco de inversion boutique en Bogota. Un fondo de private equity evalua una posicion en Grupo Nutresa (BVC: NUTRESA). Tu MD necesita un investment memo de 2 paginas. Normalmente esto toma 2 semanas con un equipo. Tu tienes 60 minutos y un equipo de agentes IA.

## Arquitectura: Pipeline Diamante

```
FASE 1: SCREENING (Secuencial, 1 agente)
──────────────────────────────────────────
  [empresa.md + mi-contexto.md]
          |
          v
  ┌───────────────────┐
  │ AGENTE 1:         │
  │ "El Screener"     │   <- Workspace 1
  │ (Junior Analyst)  │
  └─────────┬─────────┘
            v
  [screening.md]

  CHECKPOINT HUMANO 1
  -> Escribe notas-screening.md (angulo + preguntas clave)

FASE 2: DEEP DIVE (Paralelo, 3 agentes)
──────────────────────────────────────────
  [screening.md + notas-screening.md]
          |
   ┌──────┼──────────────────┐
   v      v                  v
┌────────────┐ ┌────────────┐ ┌────────────────┐
│ AG. 2:     │ │ AG. 3:     │ │ AG. 4:         │
│"El Finan-  │ │"El Strate- │ │"El Risk        │
│ ciero"     │ │ ga de      │ │ Analyst"       │  <- Workspaces 2-4
│(Financial) │ │ Industria" │ │(Risk & ESG)    │
└─────┬──────┘ └─────┬──────┘ └──────┬─────────┘
      v              v               v
analisis-        analisis-       analisis-
financiero.md    industria.md    riesgos.md

  CHECKPOINT HUMANO 2 <- DECISION CLAVE
  -> Escribe tesis.md (tu recomendacion: comprar/esperar/evitar)

FASE 3: INVESTMENT COMMITTEE (Paralelo, 3 criticos)
──────────────────────────────────────────
  [tesis.md + los 3 analisis]
          |
   ┌──────┼──────────────────┐
   v      v                  v
┌────────────┐ ┌────────────┐ ┌────────────────┐
│ PATRICIA   │ │ SANTIAGO   │ │ EL CLIENTE     │
│ Managing   │ │ Head of    │ │ (PE Fund       │
│ Director   │ │ Risk &     │ │  Partner)      │  <- Workspaces 5-7
│ (Dealmaker)│ │ Compliance │ │                │
└─────┬──────┘ └─────┬──────┘ └──────┬─────────┘
      v              v               v
critica-         critica-        critica-
md.md            risk.md         cliente.md

  CHECKPOINT HUMANO 3 <- EL MOMENTO CLAVE
  -> Escribe notas-comite.md (acepta/rechaza cada critica con razon)

FASE 4: INVESTMENT MEMO (Secuencial, 1 agente)
──────────────────────────────────────────
  [tesis.md + analisis + criticas + notas-comite.md]
          |
          v
  ┌───────────────────┐
  │ AGENTE 8:         │
  │ "El Senior        │   <- Workspace 8
  │  Analyst"         │
  └─────────┬─────────┘
            v
  [memo-final.md]

  CHECKPOINT HUMANO 4
  -> Quick polish. Done.
```

**Esto NO es un solo prompt.** Es un pipeline de 4 fases con 8 agentes y 4 momentos donde TU juicio humano cambia el resultado. Mismos agentes + diferente orquestador = tesis diferente. ESO es el Delta.

## Setup

1. Descargar [Google Antigravity](https://antigravity.google)
2. Abrir **Agent Manager** (no Editor)
3. Clonar este repo:
   ```bash
   git clone https://github.com/scarlettdetekelala/seminario-multi-agentes.git
   ```
4. Editar `mi-contexto.md` con TU informacion real

## Paso a Paso

### Fase 1: Screening (~8 min)
1. Crear 1 workspace con `empresa.md` + `mi-contexto.md`
2. Lanzar el Screener con el prompt de `prompts/agente-1-screener.md`
3. **CHECKPOINT:** Leer `screening.md`, escribir `notas-screening.md` con tu angulo y preguntas

### Fase 2: Deep Dive (~10 min)
4. Crear 3 workspaces (uno por analista)
5. Copiar `empresa.md` + `screening.md` + `notas-screening.md` a cada uno
6. Lanzar los 3 analistas **EN PARALELO** con los prompts de `prompts/agente-2-*.md`, `agente-3-*.md`, `agente-4-*.md`
7. **CHECKPOINT:** Leer los 3 analisis, **FORMAR TU TESIS**, escribir `tesis.md`

### Fase 3: Investment Committee (~8 min)
8. Crear 3 workspaces (uno por critico)
9. Copiar `tesis.md` + los 3 analisis a cada uno
10. Lanzar los 3 criticos **EN PARALELO** con los prompts de `prompts/critico-*.md`
11. **CHECKPOINT:** Leer las 3 criticas, **CURAR** (aceptar/rechazar cada una con razon), escribir `notas-comite.md`

### Fase 4: Investment Memo (~7 min)
12. Crear 1 workspace con TODOS los archivos
13. Lanzar el integrador con el prompt de `prompts/agente-integrador.md`
14. **CHECKPOINT:** Quick polish de `memo-final.md`

## Archivos

```
empresa.md                          <- Brief de Grupo Nutresa (pre-loaded)
mi-contexto.md                      <- Editar con TU perfil

prompts/
   agente-1-screener.md             <- Fase 1: Screening inicial
   agente-2-financiero.md           <- Fase 2: Analisis financiero
   agente-3-industria.md            <- Fase 2: Industria y competencia
   agente-4-riesgo.md               <- Fase 2: Riesgos y ESG
   critico-1-md.md                  <- Fase 3: Patricia (Managing Director)
   critico-2-risk.md                <- Fase 3: Santiago (Head of Risk)
   critico-3-cliente.md             <- Fase 3: El Cliente PE
   agente-integrador.md             <- Fase 4: Memo final

resultados/                         <- Aqui guardan sus resultados
presentacion.html                   <- Slides del seminario
```

## Reglas

- Minimo **3 agentes en paralelo** (en Fase 2 O Fase 3)
- **DEBES escribir tu tesis** ANTES de lanzar los criticos
- **DEBES aceptar/rechazar** cada critica CON razon
- Entregable: `memo-final.md` (no archivos sueltos)
- **Bonus:** Medir Delta — mismo pipeline, diferente analista = diferente recomendacion?

## Timing (60 min)

| Fase | Tiempo | Tu haces | Agentes hacen |
|------|--------|----------|---------------|
| 0. Setup | 5 min | Llena mi-contexto.md, abre Antigravity | -- |
| 1. Screening | 8 min | Lanza Agente 1, monitorea | Busca datos clave, noticias |
| H1 | 3 min | Lee screening, escribe angulo + preguntas | -- |
| 2. Deep Dive | 10 min | Lanza 3 agentes en paralelo | Cada uno investiga desde su lente |
| H2 | 7 min | Lee los 3, FORMA TU TESIS | -- |
| 3. Committee | 8 min | Lanza 3 criticos en paralelo | Cada uno desafia tu tesis |
| H3 | 7 min | Lee criticas, CURA (acepta/rechaza) | -- |
| 4. Memo | 7 min | Lanza integrador | Produce investment memo |
| H4 + Debrief | 5 min | Revisa memo, reflexion sobre Delta | -- |

**Tiempo activo del estudiante: 22+ min en 4 checkpoints** (no es lanzar y esperar).

## Creditos
Seminario de Complejidad · Business Cyborgs · Camilo Serna Zamora · Febrero 2026
