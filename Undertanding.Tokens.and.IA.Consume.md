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
# 🧠 Rules vs Skills para eficiencia de tokens

## Objetivo

Determinar qué mecanismo usar para optimizar consumo de tokens y costo total.

---

## Definiciones

### Rule

Comportamiento global que se aplica automáticamente en todas las interacciones.

---

### Skill

Instrucción específica para resolver un tipo de tarea particular.

---

## Diferencias clave

| Aspecto | Rule | Skill |
|--------|------|------|
| Alcance | Global | Específico |
| Activación | Automática | Manual |
| Uso | Siempre | Condicional |
| Impacto | Reducción constante | Optimización puntual |

---

## Cuándo usar Rules

- reducción general de tokens
- control de verbosidad
- estructura de respuestas
- consistencia global
- agentes y automatización

---

## Cuándo usar Skills

- tareas repetitivas
- coding
- debugging
- extracción de datos
- análisis estructurado

---

## Estrategia recomendada

```
Rule (base global)
    ↓
Skill (según tarea)
    ↓
Command (si se repite)
```

---

## Insight clave

Rule define comportamiento.

Skill define ejecución.

---

## Conclusión

Para optimización de tokens:

Rule es obligatorio.

Skill es complementario.

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

# 🧠 Commands y eficiencia de tokens

## Qué son

Un command es una acción predefinida que encapsula:

- prompt
- reglas
- contexto
- comportamiento esperado

Ejemplo:

/normalize-tickers

---

## Impacto en tokens

Los commands no reducen tokens internos del modelo.

Reducen:

- tokens de input
- repetición
- iteraciones

---

## Beneficios

- evita repetir prompts largos
- reduce ambigüedad
- mejora consistencia
- permite usar modelos más baratos
- reduce errores

---

## Principal ahorro

El mayor impacto viene de:

reducción de iteraciones

no solo de tokens por llamada

---

## Cuándo usar

- tareas repetitivas
- automatización
- pipelines
- coding iterativo
- workflows estructurados

---

## Cuándo NO usar

- tareas únicas
- análisis complejos
- problemas ambiguos

---

## Buenas prácticas

- mantenerlos cortos
- evitar ejemplos largos
- ser específicos
- definir claramente el output
- no sobrecargar lógica

---

## Mala práctica

commands grandes que:

- contienen mucho texto
- replican prompts completos
- no reducen ambigüedad

---

## Regla clave

Si lo escribís más de dos veces, debería ser un command

---

## Insight

Commands optimizan el input.
Skills optimizan el comportamiento.

La combinación de ambos maximiza eficiencia.

---
# 🗣️ Fórmulas discursivas y consumo de tokens

## Qué son

Expresiones de cortesía o relleno en prompts, por ejemplo:

- "Buen día"
- "Por favor"
- "Gracias"
- "Excelente trabajo"
- "Podrías ayudarme con..."
- "Te agradecería si..."

---

## Impacto en tokens

Sí, consumen tokens.

Cada palabra adicional:

- aumenta el input
- incrementa el costo
- no mejora la calidad del resultado

---

## Ejemplo

### ❌ Ineficiente

```
Buen día, por favor podrías ayudarme a normalizar tickers en este dataset, muchas gracias
```

### ✅ Eficiente

```
Normalizar tickers en dataset
```

---

## Cuándo usar cortesía

✔ interacción humana (chat, UX, customer-facing)  
✔ contextos donde el tono importa  

---

## Cuándo evitarla

❌ automatización  
❌ pipelines  
❌ scripting  
❌ llamadas API  
❌ uso intensivo / batch  

---

## Regla práctica

```
Si el modelo no necesita la frase para entender la tarea, eliminarla
```

---

## Insight clave

Las fórmulas discursivas:

- mejoran percepción humana  
- no mejoran performance del modelo  

---

## Impacto real

En escenarios de alto volumen:

- pequeñas frases → gran costo acumulado  

Ejemplo:

- +5 tokens × 1,000,000 requests = impacto significativo

---

## Recomendación

- eliminar cortesía en prompts técnicos  
- usar prompts directos y estructurados  
- agregar tono solo en la capa de UI si es necesario  

---

## Regla final

```
Ser educado es gratis entre humanos.
Con IA, cada palabra tiene costo.
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

# 💻 Composer (Cursor) y eficiencia de tokens

## Qué es Composer

Composer es una capa de orquestación sobre modelos de IA que:

- analiza el repositorio
- identifica partes relevantes
- envía contexto mínimo al modelo
- aplica cambios de forma incremental (diff)

---

## Cómo funciona

1. Analiza estructura del código (archivos, funciones, imports)
2. Selecciona solo el contexto relevante
3. Envía fragmentos al modelo (no archivos completos)
4. Genera cambios puntuales
5. Aplica modificaciones incrementalmente

---

## Por qué reduce tokens

### 1. Context slicing

Envía solo partes relevantes del código.

Ejemplo:

- sin Composer → archivo completo (miles de tokens)
- con Composer → función específica (decenas o cientos)

---

### 2. Diff en lugar de reescritura completa

- modifica solo lo necesario
- evita regenerar todo el archivo

---

### 3. Menos iteraciones

- mantiene contexto del repo
- no requiere reexplicar el problema
- reduce cantidad de llamadas al modelo

---

### 4. Contexto implícito

Usa información estructural del código:

- referencias
- dependencias
- imports

Esto no se envía como tokens.

---

### 5. Orquestación por pasos

Divide problemas grandes en subtareas pequeñas:

- cada llamada usa menos tokens
- mayor eficiencia global

---

## Qué NO hace

Composer no:

- reduce el precio por token
- mejora el modelo subyacente
- elimina costo si el uso es ineficiente

---

## Cuándo usar Composer

✔ refactors  
✔ debugging  
✔ cambios incrementales  
✔ repos grandes  
✔ desarrollo iterativo  

---

## Cuándo NO usar

❌ diseño conceptual  
❌ análisis teórico  
❌ prompts únicos  
❌ tareas fuera de código  

---

## Insight clave

Composer reduce tokens porque reduce el contexto enviado,
no porque reduzca el costo del modelo.

---

## Regla práctica

Si el problema es código y se puede resolver en partes:

→ usar Composer

Si el problema es conceptual:

→ usar modelo directo
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
