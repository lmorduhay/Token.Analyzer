# 🧠 Cursor Models & Composer Guide
## Choosing the Right Model Based on Cost, Accuracy and Use Case

---

# 🎯 Objective

Understand:

- What **Auto** and **MAX Mode** do.
- How **Composer** works internally.
- The strengths of each available model.
- Which model to use depending on the task.
- How to maximize quality while minimizing cost.

---

# Auto Mode

## What it is

Auto is Cursor's intelligent routing mode.

Instead of selecting a specific model yourself, Cursor automatically chooses the most appropriate underlying model for the current task.

It likely considers:

- Prompt type
- Repository size
- Context length
- Required reasoning depth
- Tool usage
- Provider availability
- Cost
- Latency

---

## Advantages

- No manual model selection.
- Good balance between quality and cost.
- Automatically benefits from Cursor infrastructure improvements.

---

## Disadvantages

- You don't know exactly which model answered.
- Cost prediction is harder.
- Less reproducible results.

---

## Best Use Cases

- Daily development
- General coding
- Mixed workloads
- Teams

---

# MAX Mode

## What it is

MAX Mode is **not a model**.

It is an execution strategy.

When enabled, Cursor prioritizes:

- reasoning quality
- larger context
- deeper analysis
- better accuracy

over

- latency
- cost

---

## What probably changes internally

MAX Mode may:

- choose stronger models
- allow larger context windows
- reduce context compression
- perform more reasoning steps
- execute more internal orchestration

---

## Advantages

- Better answers
- Better architecture decisions
- Better debugging
- Better planning

---

## Disadvantages

- Higher token usage
- Higher cost
- Increased latency

---

## Recommended Usage

Enable MAX only for:

- architecture
- difficult debugging
- research
- important decisions
- complex reasoning

Leave disabled for routine coding.

---

# Understanding Composer

## What Composer is

Composer is **not an LLM**.

It is an orchestration layer built on top of one or more language models.

Its responsibilities include:

- repository understanding
- retrieval
- context selection
- planning
- diff generation
- incremental implementation

---

## Internal Workflow

Composer approximately performs:

```
User Prompt
      ↓
Repository Analysis
      ↓
Context Retrieval
      ↓
Planner
      ↓
Underlying LLM
      ↓
Diff Generation
      ↓
Apply Changes
```

---

## Why Composer Reduces Token Usage

### 1. Context Slicing

Instead of sending entire files, Composer only sends relevant portions.

Example:

Without Composer

```
AuthenticationService.cs
2,500 lines
```

With Composer

```
AuthenticateUser()
120 lines
```

Huge reduction in input tokens.

---

### 2. Diff-Based Editing

Instead of regenerating complete files, Composer generates only the modifications.

Lower output token usage.

---

### 3. Repository Awareness

Composer already knows:

- imports
- references
- dependencies
- file relationships

You don't need to explain these repeatedly.

---

### 4. Reduced Iterations

Because Composer understands project structure, it usually requires fewer back-and-forth interactions.

This often produces greater savings than token reduction itself.

---

### 5. Multi-Step Orchestration

Large problems are decomposed into smaller subtasks.

Each model invocation becomes smaller and cheaper.

---

# What Composer Does NOT Do

Composer does NOT:

- reduce model pricing
- make the underlying model smarter
- magically improve poor prompts

Instead, it minimizes unnecessary context.

---

# Composer for Non-Coding Tasks

Composer still works for:

- architecture
- design
- planning
- reasoning

However, its advantages diminish.

Why?

Because there is:

- no repository to retrieve
- no diffs
- no code locality
- no implementation context

In those cases, orchestration overhead provides little value.

---

## Recommendation

### Use Composer for

- coding
- refactoring
- debugging
- Apps Script
- automation
- incremental implementation

### Prefer Direct Models for

- architecture
- finance
- strategy
- research
- conceptual reasoning

---

# Underlying Model Selection

When Composer is selected without manually choosing a model, Cursor most likely performs dynamic routing.

The exact implementation is proprietary, but it probably considers:

- prompt complexity
- repository size
- required context
- latency
- provider cost
- provider availability

---

## Likely Internal Routing

Most probable architecture:

```
Planner
      ↓
Retriever
      ↓
Model Router
      ↓
Reasoning Model
      ↓
Diff Generator
```

---

## Most Likely Default Models

Based on public behavior and observed performance:

| Probability | Model |
|------------|---------|
| Very High | Claude Sonnet |
| High | GPT-5.x Coding Variants |
| Medium | Gemini (large context) |
| Low | Lightweight planning models |

Cursor likely optimizes for:

```
Minimum infrastructure cost
while maintaining acceptable quality.
```

---

# Model Comparison

| Model | Quality | Cost | Speed | Best Use |
|--------|---------|------|--------|----------|
| Composer 2.5 Fast | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Coding, Apps Script, Debugging |
| Sonnet 5 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | General Software Development |
| Opus 4.8 | ⭐⭐⭐⭐⭐⭐ | ⭐ | ⭐⭐ | Architecture, Research, Finance |
| GPT-5.6 Sol | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | General Purpose |
| GPT-5.6 Terra | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | Large Context Analysis |
| GPT-5.5 | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | Automation |
| Cursor Grok 4.5 Fast | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Fast Interaction |
| Fable 5 | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | Creative Writing |

*(More stars = better for that dimension.)*

---

# Recommended Model by Task

| Task | Recommended Model |
|------|--------------------|
| Apps Script | Composer |
| Google Sheets Automation | Composer |
| Refactoring | Composer |
| Debugging | Composer |
| Python | Composer |
| C# | Composer |
| New Project | Sonnet |
| Architecture | Opus |
| Financial Analysis | Opus |
| Research | Opus |
| Technical Documentation | Sonnet |
| Automation | GPT-5.5 |
| General Chat | GPT-5.6 Sol |
| Brainstorming | Fable |
| Fast Questions | Grok |
| Mixed Workloads | Auto |

---

# Recommended Personal Strategy

For a software engineer working with:

- Apps Script
- Google Sheets
- Finance
- Automation
- Trading
- Portfolio Analysis

Recommended usage:

| Model | Usage |
|--------|------|
| Composer | 70% |
| Sonnet | 20% |
| Opus | 8% |
| GPT/Grok/Fable | 2% |

---

# Cost Optimization Strategy

Use the strongest model only where reasoning quality matters.

Suggested workflow:

```
Architecture
        ↓
Opus

Implementation
        ↓
Composer

Validation
        ↓
Sonnet

Automation
        ↓
GPT-5.5
```

---

# Key Insights

## Composer

Composer does not reduce the model price.

Composer reduces:

- context size
- repeated prompts
- iterations

which usually reduces total cost.

---

## Auto

Auto optimizes the workflow for you.

Best for users who don't want to manage model selection.

---

## MAX Mode

MAX optimizes quality.

Not cost.

---

## Final Recommendation

For most professional developers:

- **Auto** → everyday work.
- **Composer** → implementation, debugging, refactoring.
- **Sonnet** → general software engineering.
- **Opus** → architecture, finance and strategic reasoning.
- **MAX Mode** → only when quality is significantly more important than cost.

---

# Final Principle

```
Use the cheapest model capable of solving the current problem with sufficient quality.

Escalate only when:
- reasoning depth,
- ambiguity,
- or business impact
justify the additional cost.
```