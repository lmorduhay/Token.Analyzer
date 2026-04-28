# 🧠 Cómo se convierten prompts en tokens

## Concepto básico

Los modelos no procesan texto directamente, sino **tokens**.

Un token puede ser:
- palabra
- parte de palabra
- símbolo
- espacio

---

## Tokenización de input

Ejemplo:

"Normalize tickers in a Google Sheet"

No equivale a número de palabras → puede ser 10–12 tokens.

---

## Reglas aproximadas

- Inglés: 1 token ≈ 4 caracteres
- Español: 1 token ≈ 3–3.5 caracteres

---

## Qué cuenta como input tokens

El input total incluye:

1. Prompt del usuario  
2. System prompt (instrucciones ocultas)  
3. Historial de conversación  
4. Contexto adicional (archivos, imágenes, código)

---

### Fórmula

Input tokens = prompt + system + history + context

---

## Output tokens

El modelo genera texto token por token:

1. Lee input
2. Predice siguiente token
3. Repite hasta completar respuesta

---

## Costos

Generalmente:

- Input tokens → más baratos
- Output tokens → más caros

Ejemplo:

- Input: $1 / 1M tokens  
- Output: $5 / 1M tokens  

---

## Implicación clave

Reducir output tiene más impacto en costo que reducir input.

---

## Factores que aumentan tokens

### Input

- prompts largos
- contexto repetido
- código completo
- archivos sin filtrar

### Output

- explicaciones largas
- ejemplos innecesarios
- formato no controlado

---

## Buenas prácticas

- usar prompts compactos
- estructurar input (objetivo + restricciones)
- limitar output explícitamente
- evitar repetir contexto
- usar archivos/RAG para inputs grandes

---

## Insight clave

Más texto ≠ mejor resultado

Calidad depende de:
- claridad
- estructura
- constraints

---

## Prioridad de optimización

1. Reducir output tokens  
2. Reducir iteraciones  
3. Reducir input redundante  
4. Elegir modelo adecuado  

---

## Conclusión

El costo real depende de:

tokens × iteraciones × precio por modelo