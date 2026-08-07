# AI FDE Learning Lab

A hands-on learning repository for building an **AI Forward Deployed Engineer / Solution Architect** skill stack with a strong data-engineering foundation.

## Learning philosophy

**Learn → understand → implement from scratch → visualize → use a library → apply to a domain → break → rebuild.**

This repository intentionally combines:

- Python foundations
- Statistics and machine learning
- Generative AI / LLM systems
- RAG and agentic workflows
- FDE architecture and delivery thinking
- Pharma AI applications using public/synthetic data
- PlantMind 2.0 as a cross-domain industrial AI learning track

> Safety rule: keep this repository free of client/LTTS/Jazz proprietary data, credentials, documents, code, and secrets. Use only public, synthetic, or personally owned learning assets.

## Repository map

```text
ai-fde-learning-lab/
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   ├── 00_learning_dashboard.ipynb
│   ├── 00_python_to_ml_bridge.ipynb
│   ├── 01_ml_foundations.ipynb
│   ├── 02_simple_linear_regression.ipynb
│   ├── 03_multiple_linear_regression.ipynb
│   └── 04_model_evaluation_r2.ipynb
│
├── notes/
│   ├── LESSON_DNA_TEMPLATE.md
│   ├── 2026-08-07_regression_learning_session.md
│   └── ai_commando_learning_map.md
│
├── data/
│   └── README.md
│
└── projects/
    ├── pharma-ai/
    │   └── README.md
    └── plantmind-2/
        └── README.md
```

## Why GitHub sits in the middle

GitHub is not only code storage for this project. It is the **learning memory layer**.

Important lessons from course audio, ChatGPT discussion, handwritten exercises, Copilot experiments, VS Code work, and Colab should eventually be converted into version-controlled artifacts here.

That means we preserve not just final syntax, but also:

- definitions
- intuition
- arithmetic
- mistakes and corrections
- why a formula works
- what a library call hides
- data-engineering analogies
- pharma/PlantMind applications
- exercises and explain-back checkpoints

## How to use this repo

### Google Colab
Open a notebook from GitHub in Colab and run it in the browser. Use Colab as the **cloud execution lab**.

### VS Code
Clone the repository locally and use the Microsoft **Python** and **Jupyter** extensions. Use VS Code as the **local development workspace**.

```bash
git clone https://github.com/1celestial0/ai-fde-learning-lab.git
cd ai-fde-learning-lab
code .
```

### Sync rule
GitHub is the **single source of truth**.

Before starting work locally:

```bash
git pull
```

After a learning session:

```bash
git add .
git commit -m "Practice: describe what you learned"
git push
```

Avoid editing the same notebook in Colab and VS Code at the same time.

## 13-part Lesson DNA

Every important new lesson should try to preserve:

1. Source / course context
2. Core definition
3. Plain-English mental model
4. Analogy / visual intuition
5. Mathematics / arithmetic from the root
6. From-scratch Python
7. Visualization + interpretation
8. Library / production implementation
9. Data-engineering connection
10. Pharma + PlantMind application
11. Corrections / failure modes / outdated APIs
12. Rebuild + break exercises
13. Explain-back / mastery / gap log

See `notes/LESSON_DNA_TEMPLATE.md` for the full standard.

## Current learning node

**Python → ML Foundations → Simple Linear Regression → Multiple Linear Regression → Model Evaluation / R²**

The immediate objective is not to memorize APIs. It is to understand what `fit()`, `predict()`, residuals, SSE/MSE/RMSE, train/test split, coefficients, intercepts, and R² actually mean.

## Current preserved session

`notes/2026-08-07_regression_learning_session.md` captures the full reasoning journey from:

- numerical vs categorical data
- supervised/unsupervised/reinforcement learning
- X/Y mental model
- handwritten list/index/loop practice
- means and deviations
- slope derivation
- intercept and predictions
- residuals and squared error
- multiple regression
- encoding
- train/test split
- `fit()` / `predict()`
- R² interpretation

This repository should continue to grow as the AI Commando and FDE learning journey progresses.
