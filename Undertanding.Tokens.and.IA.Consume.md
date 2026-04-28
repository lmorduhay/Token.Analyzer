# 🧠 Token Efficiency Protocol & AI Model Usage Guide

---

# 🎯 Objetivo

Minimizar el costo total del uso de IA manteniendo calidad suficiente.

```
Costo total = tokens × iteraciones × precio del modelo
```

---

# 🔬 Cómo funcionan los tokens

## Qué es un token

Un token es una unidad de texto que puede ser:

- palabra
- parte de palabra
- símbolo
- espacio

---

## Aproximaciones útiles

- Inglés → 1 token ≈ 4 caracteres  
- Español → 1 token ≈ 3–3.5 caracteres  

👉 Español consume más tokens.

---

## Input tokens (lo que pagás)

Incluye:

- prompt del usuario
- system prompt (instrucciones invisibles)
- historial de conversación
- archivos / imágenes / código

```
Input = prompt + system + history + contexto
```

---

## Output tokens

El modelo genera texto token por token.

👉 Generalmente:

- input → más barato  
- output → más caro  

---

## Insight clave

```
Reducir output > reducir input
```

---

# 💸 Qué realmente impacta el costo

Prioridad real:

1. Reducir output innecesario  
2. Reducir iteraciones  
3. Reducir input redundante  
4. Elegir modelo correcto  

---

# 🧠 Skills (uso correcto)

## Qué son

Patrones reutilizables que evitan repetir instrucciones.

---

## Cuándo usar

✔ tareas repetitivas  
✔ automatización  
✔ pipelines  
✔ coding iterativo  

---

## Cuándo NO usar

❌ tareas únicas  
❌ análisis estratégico  
❌ problemas altamente ambiguos  

---

## Beneficios

- menos tokens por prompt  
- menos errores  
- menos iteraciones  
- permite usar modelos más baratos  

---

## Riesgos

- skills grandes → aumentan tokens  
- sobreingeniería → más llamadas  
- mala definición → peor output  

---

## Regla clave

```
Si repetís → usar skill
Si es único → prompt directo
```

---

# ⚙️ Buenas prácticas de prompts

## Estructura óptima

```
Objetivo:
Contexto mínimo:
Restricciones:
Output esperado:
Criterios de aceptación:
```

---

## Input eficiente

- no repetir contexto  
- no pegar documentos completos  
- usar archivos cuando el contenido es largo  
- usar RAG cuando sea necesario  
- enviar solo fragmentos relevantes  

---

## Output eficiente

- limitar longitud explícitamente  
- usar JSON cuando sea posible  
- evitar explicaciones largas  
- evitar ejemplos innecesarios  

---

## Ejemplo

### ❌ Ineficiente

```
Explicación larga + redundancia
```

### ✅ Eficiente

```
Objetivo: normalizar tickers
Restricciones: no romper fórmulas
Output: script final + validación
```

---

# 🧠 Selección de modelo (visión general)

## Regla principal

```
Elegir el modelo más barato que cumpla con la calidad mínima requerida
```

---

# 📊 Comparativa simplificada de modelos

| Tipo de modelo | Costo | Calidad | Velocidad | Uso ideal |
|------|--------|--------|--------|--------|
| Nano / Lite | Muy bajo | Baja | Muy alta | Clasificación, parsing |
| Mini / Flash | Bajo | Media | Alta | Automatización, código simple |
| Standard | Medio | Alta | Media | Uso general |
| High-tier | Alto | Muy alta | Baja | Razonamiento complejo |

---

# 💰 Costos típicos (orden de magnitud)

| Modelo | Input ($/1M tokens) | Output ($/1M tokens) |
|--------|-------------------|----------------------|
| Nano | ~0.05 | ~0.4 |
| Mini | ~0.25 | ~2 |
| Standard | ~1–3 | ~10–15 |
| High-tier | ~5 | ~25 |

👉 Output es mucho más caro → optimizar salida es clave.

---

# 🧠 Cuándo usar cada tipo de modelo

## 🟢 Modelos baratos (nano / mini)

Usar para:

- clasificación
- extracción
- transformación de datos
- regex / parsing
- automatización masiva

👉 mejor ROI

---

## 🟡 Modelos intermedios

Usar para:

- código simple/medio
- prompts bien definidos
- tareas repetibles

---

## 🔴 Modelos caros (high-tier)

Usar para:

- decisiones complejas
- arquitectura
- finanzas
- debugging difícil
- prompts ambiguos

👉 caros por token, pero pueden reducir iteraciones

---

# 💻 Coding: herramientas vs modelos

## Herramientas tipo IDE (ej: Composer / Cursor)

Ventajas:

- trabajan sobre diffs
- usan contexto del repo
- reducen tokens repetidos
- más eficientes en iteración

---

## Cuándo usar herramientas de coding

✔ refactors  
✔ debugging  
✔ cambios incrementales  
✔ repos grandes  

---

## Cuándo usar modelos “puros”

✔ diseño de arquitectura  
✔ análisis conceptual  
✔ planificación  

---

## Insight clave

```
Herramientas coding reducen tokens más que modelos más baratos
```

---

# ⚡ Estrategia óptima (muy importante)

## Flujo ideal

1. Modelo fuerte → define solución  
2. Modelo barato / herramienta → implementa  
3. Iteraciones mínimas  

---

## Anti-pattern

```
Usar modelo caro para todo
```

---

# 🔁 Iteraciones vs costo

Ejemplo:

- Modelo barato × 5 iteraciones → más caro  
- Modelo caro × 1 iteración → más barato  

👉 siempre medir costo total

---

# 🚀 Uso de archivos vs texto

## Usar archivos cuando:

- input > 3k–5k tokens  
- documentos largos  
- datasets  
- logs  

---

## Usar texto cuando:

- contexto corto  
- instrucciones simples  

---

## Imágenes

- útiles para UI / gráficos  
- caras en tokens  

---

# ⚡ Rules globales (para agentes)

## Principios

- ser conciso  
- evitar redundancia  
- priorizar output estructurado  
- minimizar iteraciones  

---

## Modo coding

- devolver código directo  
- evitar explicación innecesaria  
- trabajar en diffs  

---

## Modo agresivo

- output mínimo  
- JSON/code-only  
- cero narrativa  

---

# 🧠 Insight final

```
El modelo no mejora por más texto.
Mejora por mejor estructura.
```

---

# 📌 Regla principal

```
Optimizar tokens no es escribir menos.
Es comunicar mejor con menor costo total.
```