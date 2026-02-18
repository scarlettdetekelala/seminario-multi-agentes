# 🧠 Paso Final: Integrador

## Cuándo usarlo
Cuando los 3 agentes anteriores hayan terminado.

## Setup
1. Crea un workspace nuevo (o usa uno existente)
2. Copia los 3 archivos generados: `investigacion.md`, `analisis-gaps.md`, `plan-estudio.md`
3. Inicia una conversación con este prompt:

---

```
Tengo 3 documentos generados por agentes independientes:
- investigacion.md — mercado laboral y tendencias
- analisis-gaps.md — mis fortalezas y gaps
- plan-estudio.md — cursos y recursos disponibles

Tu tarea:
1. Lee los 3 documentos
2. Identifica contradicciones o inconsistencias entre ellos
3. Genera un plan de estudio INTEGRADO que:
   - Priorice los gaps más urgentes (del análisis) 
   - Alinee con las tendencias del mercado (de la investigación)
   - Use los mejores recursos disponibles (del plan)
4. Genera el resultado final como `plan-final.md`

Incluye:
- Resumen ejecutivo (1 párrafo)
- Plan semestre por semestre con justificación
- Top 5 acciones para empezar esta semana
- Métricas para medir progreso cada 3 meses
```

---

## ¿Por qué un cuarto agente?
Los 3 agentes trabajaron en paralelo sin conocer los resultados de los otros. El integrador es donde TÚ como orquestador agregas el valor — combinas perspectivas independientes en algo coherente. Esto es lo que un solo prompt no puede hacer.
