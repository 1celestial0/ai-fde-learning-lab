# Learning Notebook DNA — Standard for Every Lesson

This repository is not a code dump. Every important lesson should preserve **how the concept was understood**, not only the final syntax.

## The 13-part lesson DNA

### 1. Source / Course Context
- What module/video/course introduced the concept?
- What problem was the instructor trying to solve?
- What came immediately before and after it?

### 2. Core Definition
- Precise definition.
- Important terminology and notation.
- What the concept is **not**.

### 3. Plain-English Mental Model
- Explain it without mathematical jargon.
- Reduce the idea to one reusable sentence.

### 4. Analogy / Visual Intuition
- Ruler through points, buckets, pipelines, tables, etc.
- Prefer analogies that connect to existing data-engineering knowledge.

### 5. Mathematics / Arithmetic From the Root
- Formula.
- Meaning of every symbol.
- Work at least one tiny example manually.
- Translate sigma/aggregation notation into row-level arithmetic.

### 6. From-Scratch Python
- Use basic Python first when practical.
- Show loops, variables, functions, accumulators, lists/dictionaries explicitly.
- Comments should explain **why**, not merely repeat the syntax.

### 7. Visualization + Interpretation
- Create a visual when it helps.
- Always include: **What am I supposed to notice?**
- A chart without interpretation is incomplete.

### 8. Library / Production Version
- NumPy / Pandas / scikit-learn / PyTorch / relevant framework.
- Explain what the library call hides under the hood.
- Keep current APIs; flag outdated course APIs.

### 9. Data Engineering Connection
Connect the new idea to known concepts such as:
- row grain
- SQL `SUM()` / `AVG()`
- joins / keys
- feature tables
- pipelines
- data quality
- lineage
- batch vs serving

### 10. Dual-Domain Application
For important concepts, ask both:
- **Pharma:** where could this solve a public/synthetic pharma problem?
- **PlantMind:** where could this solve an industrial/sensor problem?

This keeps pharma as a specialization without making the engineering skills domain-locked.

### 11. Corrections / Failure Modes / Things That Can Mislead
- Simplifications in the course.
- Deprecated APIs.
- Common misconceptions.
- Data leakage, causation vs correlation, metric misuse, etc.

### 12. Exercise — Rebuild and Break
Use at least two modes:
- **Rebuild:** reproduce the concept without looking.
- **Break:** change/remove something and predict what will happen before running it.

### 13. Explain-Back / Mastery / Gap Log
A lesson is not complete until the learner can explain it in their own words.

Record:
- one-sentence explanation
- what still feels magical
- questions to revisit
- next concept that depends on this one

---

## Coding style for this learning repository

- Prefer small cells with one learning objective.
- Use comments that explain intent and reasoning.
- Keep outputs readable.
- Do not hide basic mechanics too early behind helper libraries.
- Once the mechanics are understood, show the professional library implementation.
- Use public/synthetic data only; never place LTTS/Jazz/client-sensitive information or credentials in this public repository.

## Learning sequence

```text
Listen / capture course
        ↓
Preserve raw idea
        ↓
Correct misconceptions
        ↓
Understand arithmetic
        ↓
Code from scratch
        ↓
Visualize
        ↓
Use library
        ↓
Apply to Pharma + PlantMind
        ↓
Exercise
        ↓
Explain back
        ↓
Commit to GitHub
```

This file is the quality standard for every new notebook added to the lab.
