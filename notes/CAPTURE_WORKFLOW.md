# Capture Workflow — ChatGPT, Copilot, Course Notes, Colab, VS Code

The goal is to preserve useful learning from multiple tools without turning the public repository into an uncontrolled dump.

## Source-of-truth rule

**GitHub is the permanent memory layer.**

Useful learning can originate from:
- ChatGPT conversations
- AI Commando course/audio
- handwritten practice
- LTTS Copilot learning prompts
- Google Colab experiments
- VS Code exercises
- public documentation / tutorials

Before anything is committed, convert it into a clean learning artifact using the Lesson DNA.

## Safe capture from LTTS Copilot

Because LTTS Copilot may have company-data integration, **do not automatically copy its output into this public GitHub repository**.

Only capture material when you are certain it contains:
- generic/public technical knowledge
- your own non-confidential notes
- synthetic examples
- no client/company names, secrets, credentials, proprietary code, internal documents, or sensitive data

When in doubt, do not commit it.

## Simple manual workflow

1. In Copilot, generate a generic/public learning explanation.
2. Review it for company/client-sensitive information.
3. Save the safe content locally as Markdown, e.g.:

```text
notes/inbox/copilot_gradient_descent.md
```

4. In VS Code:

```bash
git pull
git add notes/inbox/copilot_gradient_descent.md
git commit -m "Capture: Copilot notes on gradient descent"
git push
```

5. Ask ChatGPT to review the new GitHub note and merge the useful parts into the correct master notebook.

## Colab workflow

- Open the master notebook from GitHub.
- Experiment in Colab.
- If the experiment is worth preserving, save/commit the notebook back to GitHub or reproduce the clean change in VS Code.
- Avoid editing the same notebook in Colab and VS Code simultaneously.

## ChatGPT workflow

Say something like:

> Update the learning lab with everything important from this lesson.

ChatGPT should:
- preserve definitions
- preserve the reasoning path
- add corrections
- add arithmetic/code
- add exercises
- update the relevant notebook and/or session note

## Raw capture vs mastered knowledge

```text
RAW / INBOX
course transcript, Copilot note, scratch experiment
            ↓
REVIEW
remove noise + sensitive material + errors
            ↓
MASTER LESSON
13-part Lesson DNA notebook
            ↓
PRACTICE
rebuild / break / explain back
            ↓
COMMIT
GitHub version history
```

The repository should remain a **curated learning operating system**, not merely a backup folder.
