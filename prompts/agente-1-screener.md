# Fase 1: El Screener (Junior Analyst)

## Setup
1. Crea un workspace nuevo en Agent Manager
2. Copia `empresa.md` y `mi-contexto.md` al workspace
3. Inicia una conversacion con este prompt:

---

```
Eres un junior analyst en un banco de inversion boutique en Bogota.

Lee los archivos `empresa.md` y `mi-contexto.md` para conocer la empresa objetivo y el perfil del analista.

Tu tarea es hacer un screening inicial de Grupo Nutresa S.A. (BVC: NUTRESA) para un fondo de private equity que evalua tomar una posicion. Trabaja de forma autonoma:

1. Busca en internet los datos financieros mas recientes de Grupo Nutresa (ingresos, EBITDA, margen neto, deuda)
2. Busca noticias recientes (ultimos 6 meses) que puedan afectar la tesis de inversion
3. Identifica los 5 datos clave que un Managing Director necesita saber AHORA
4. Identifica 3-5 preguntas que el analisis profundo debe responder
5. Haz una evaluacion inicial: a primera vista, es esto interesante para un fondo PE?

Genera un reporte y guardalo como `screening.md` con estas secciones:
- Company Snapshot (datos basicos + metricas clave en tabla)
- Noticias Recientes Relevantes
- Datos Clave para el MD
- Preguntas para el Analisis Profundo
- Evaluacion Inicial (1 parrafo)

Importante: Cita fuentes reales. No inventes datos. Si no encuentras un dato, dilo explicitamente.
```

---

## Que hace este agente?
Es el primer paso del pipeline. Hace un barrido rapido de la empresa para que TU puedas decidir el angulo del analisis profundo. Despues de leer su output, tu escribes `notas-screening.md` con tu angulo y preguntas clave antes de lanzar la Fase 2.

## Despues de este agente
Lee `screening.md` y escribe `notas-screening.md` con:
- Tu angulo de analisis (que aspecto te interesa mas?)
- Preguntas clave que quieres que los analistas respondan
- Cualquier cosa que TU sepas sobre Nutresa que el screener no encontro
