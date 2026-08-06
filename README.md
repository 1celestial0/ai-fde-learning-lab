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
├── notebooks/
│   ├── 00_learning_dashboard.ipynb
│   ├── 01_python_foundations.ipynb
│   ├── 02_simple_linear_regression.ipynb
│   └── 03_multiple_linear_regression.ipynb
├── notes/
│   └── ai_commando_learning_map.md
├── data/
│   └── README.md
└── projects/
    ├── pharma-ai/
    │   └── README.md
    └── plantmind-2/
        └── README.md
```

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

## Notebook DNA

Each major learning notebook should follow this pattern:

1. 📘 Theory
2. 🧠 Intuition / analogy
3. 🔢 Mathematics
4. 💻 From-scratch Python
5. 📊 Visualization
6. ⚡ Library implementation
7. 🏗️ Data-engineering connection
8. 💊 Pharma application
9. 🌱 PlantMind application
10. 🧪 Try-it-yourself exercise
11. ✅ Validation / interpretation
12. ❓ Questions and gaps

## Current learning node

**Machine Learning Foundations → Simple Linear Regression → Multiple Linear Regression → Model Evaluation**

The first objective is not to memorize APIs. It is to understand what `fit()`, `predict()`, residuals, SSE/MSE/RMSE, train/test split, coefficients, intercepts, and R² actually mean.
