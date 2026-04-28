# 🧠 Token Efficiency Protocol & AI Model Usage Guide

## 🎯 Objetivo

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

# 🧠 Selección de modelo

## Regla general

```
Modelo más barato que cumpla calidad mínima
```

---

## Coding

- Iteración → Composer / Cursor / Codex  
- Arquitectura → modelos grandes  

---

## Automatización

- modelos pequeños (mini/nano)

---

## Razonamiento complejo

- modelos high-tier  

---

## Extracción masiva

- modelos baratos + JSON  

---

# 🧠 Composer (Cursor) — cuándo usar

## Usar

✔ edición de código  
✔ refactors  
✔ debugging  
✔ repos grandes  

---

## No usar

❌ diseño conceptual  
❌ explicación teórica  
❌ tareas no técnicas  

---

## Insight clave

Composer no reduce precio → reduce tokens.

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

## Modo agresivo (automatización)

- output mínimo  
- JSON/code-only  
- cero narrativa  

---

# 🚀 Uso de archivos vs texto

## Usar archivos cuando:

- input > ~3–5k tokens  
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