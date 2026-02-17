# 🎓 Demo: Plan de Estudio Personalizado con Multi-Agentes

## Objetivo
Usar Google Antigravity Agent Manager para crear un plan de estudio personalizado usando **3 agentes que trabajan en equipo**.

## El Problema
Eres estudiante de Ingeniería Industrial. Tienes materias pendientes, intereses específicos, y quieres optimizar tu próximo semestre. ¿Cómo decides qué estudiar, en qué orden, y con qué recursos?

## Los 3 Agentes

### 🔍 Agente 1: Investigador de Contexto
**Rol:** Analiza tu situación académica actual
- Revisa el pensum de Ingeniería Industrial
- Identifica prerrequisitos y dependencias entre materias
- Busca tendencias del mercado laboral para priorizar electivas

### 📋 Agente 2: Estratega de Plan
**Rol:** Diseña el plan optimizado
- Recibe el análisis del Agente 1
- Crea un plan semestre por semestre
- Balancea carga académica (créditos, dificultad)
- Sugiere electivas según intereses y mercado

### 📄 Agente 3: Generador de Recursos
**Rol:** Produce material de apoyo
- Recibe el plan del Agente 2
- Busca recursos gratuitos para cada materia (YouTube, MIT OCW, Coursera)
- Crea un calendario semanal sugerido
- Genera un documento final consolidado

## Cómo Correrlo

### Paso 1: Abrir Antigravity
1. Descarga Antigravity desde [antigravity.google](https://antigravity.google)
2. Instálalo y ábrelo
3. Abre esta carpeta como workspace (File → Open Folder)

### Paso 2: Configurar tu contexto
Edita el archivo `mi-contexto.md` con tu información real:
- Semestre actual
- Materias aprobadas
- Materias pendientes
- Intereses profesionales
- Horario disponible

### Paso 3: Ejecutar los agentes (uno por uno)
1. Abre el chat de Antigravity (Ctrl+L o Cmd+L)
2. Copia y pega el **Prompt del Agente 1** desde `prompts/agente-1-investigador.md`
3. Espera el resultado → se guarda en `resultados/01-analisis-contexto.md`
4. Copia y pega el **Prompt del Agente 2** → resultado en `resultados/02-plan-estudio.md`
5. Copia y pega el **Prompt del Agente 3** → resultado en `resultados/03-recursos.md`

### Paso 4: Revisar y ajustar
- Lee el plan generado
- Pide ajustes al agente ("quiero más énfasis en datos", "tengo clase los martes")
- Itera hasta que el plan te sirva

## Estructura del Proyecto
```
demo-plan-estudio/
├── README.md              ← Estás aquí
├── mi-contexto.md         ← TU información (edítalo)
├── prompts/
│   ├── agente-1-investigador.md
│   ├── agente-2-estratega.md
│   └── agente-3-recursos.md
├── resultados/
│   ├── 01-analisis-contexto.md
│   ├── 02-plan-estudio.md
│   └── 03-recursos.md
└── ejemplo/               ← Ejemplo completo ya ejecutado
    ├── contexto-ejemplo.md
    ├── 01-analisis-ejemplo.md
    ├── 02-plan-ejemplo.md
    └── 03-recursos-ejemplo.md
```

## 💡 ¿Qué estás aprendiendo?
- **Orquestación:** Un agente alimenta al siguiente (pipeline)
- **Especialización:** Cada agente tiene UN rol claro
- **Contexto > Inteligencia:** El mismo modelo con mejor contexto = mejor resultado
- **Iteración:** No es "una pregunta, una respuesta" — es conversación

---
*Business Cyborgs — Seminario de Complejidad, Feb 2026*
