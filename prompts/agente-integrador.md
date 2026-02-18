# Fase 4: El Senior Analyst (Investment Memo)

## Cuando usarlo
Despues de que los 3 criticos hayan terminado Y tu hayas escrito `notas-comite.md` con tus decisiones sobre cada critica.

## Setup
1. Crea un workspace nuevo (o usa uno existente)
2. Copia TODOS los archivos generados:
   - `empresa.md` — Brief de la empresa
   - `tesis.md` — Tu tesis de inversion
   - `analisis-financiero.md` — Analisis financiero
   - `analisis-industria.md` — Analisis de industria
   - `analisis-riesgos.md` — Analisis de riesgos
   - `critica-md.md` — Critica de Patricia (MD)
   - `critica-risk.md` — Critica de Santiago (Risk)
   - `critica-cliente.md` — Critica del Cliente PE
   - `notas-comite.md` — TUS decisiones sobre las criticas
3. Inicia una conversacion con este prompt:

---

```
Eres un senior analyst en un banco de inversion boutique en Bogota. Tu trabajo es producir el investment memo final que el Managing Director va a presentar al cliente.

Lee TODOS los archivos disponibles. Tienes:
- La tesis de inversion del analista (`tesis.md`)
- 3 analisis profundos (financiero, industria, riesgos)
- 3 criticas del Investment Committee (MD, Risk, Cliente PE)
- Las decisiones del analista lider sobre las criticas (`notas-comite.md`)

Tu tarea es escribir un investment memo profesional de 2 paginas. Guarda el resultado como `memo-final.md`.

Estructura del memo:

# Investment Memo — Grupo Nutresa S.A.
**Confidencial | [Fecha] | [Nombre del banco]**

## Resumen Ejecutivo
[1 parrafo: que es Nutresa, la recomendacion, y el dato mas importante]

## Tesis de Inversion
[La tesis del analista, fortalecida con las decisiones del comite]
[Recomendacion clara: COMPRAR / ESPERAR / EVITAR]
[Horizonte de tiempo y target de retorno]

## Analisis Financiero
[Resumen de metricas clave en tabla]
[Valoracion y senal]

## Posicion Competitiva
[Fortalezas estrategicas, moat, posicion en la industria]

## Riesgos y Mitigacion
[Top 3-5 riesgos con plan de mitigacion]
[Incluir los riesgos que el comite identifico como criticos]

## Recomendacion
[Conclusion clara con next steps]

---

Reglas:
- Maximo 2 paginas equivalentes (~1000-1200 palabras)
- Tono profesional, conciso, directo
- Integra las criticas que el analista ACEPTO en `notas-comite.md`
- Ignora las criticas que el analista RECHAZO (pero si una critica rechazada es valida, menciona por que se descarto)
- No repitas datos — resume y sintetiza
- Cada seccion debe llevar a la siguiente logicamente
```

---

## Por que un agente integrador?
Los analistas investigaron, tu formaste la tesis, los criticos desafiaron, tu curaste las criticas. Ahora el integrador toma TODAS esas capas y produce un documento profesional. El valor no esta en el documento — esta en las DECISIONES que tu tomaste en cada checkpoint y que el memo refleja.

## Despues del memo
Lee `memo-final.md` y haz un quick polish. Luego reflexiona:
1. Que aportaron los AGENTES? (datos, estructura, velocidad)
2. Que aportaste TU? (tesis, juicio sobre riesgos, decisiones)
3. Podrias haber logrado esto con UN solo prompt?
4. Si un companero corriera el mismo pipeline, llegaria a la misma recomendacion?
