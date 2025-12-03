#🔐 Privacy–Utility Trade-off in AI Code Completion

This project evaluates how different levels of code obfuscation impact the performance of AI code-completion models.

📌 Overview

AI coding assistants may unintentionally expose or depend on sensitive information embedded in source code. This project analyzes how obfuscating code affects:

Privacy → How different the obfuscated prompt is from the original

Utility → How close the generated code is to the canonical solution

Using the OpenAI HumanEval dataset, I compare:

Original prompts

Low obfuscation → Variable renaming

High obfuscation → Placeholder identifiers, removed comments, stripped docstrings

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🧠 Model

CodeT5-small from Hugging Face

Loaded and evaluated across 20 HumanEval tasks

60 completions generated (3 variants × 20 examples)

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

| Metric      | Description                                                 |
| ----------- | ----------------------------------------------------------- |
| **Utility** | ROUGE-L F1 between model output and canonical solution      |
| **Privacy** | Normalized Levenshtein distance between prompt and original |

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

📊 Results

Strong obfuscation improves privacy but significantly reduces code-completion accuracy.

Light obfuscation provides a moderate privacy boost with minimal utility loss.

A clear privacy–utility trade-off emerges (visualized via scatter plot).

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

🛠️ Tech Stack

Python

Hugging Face Transformers (CodeT5-small)

Datasets (HumanEval)

ROUGE Score

RapidFuzz (Levenshtein)

Pandas, Matplotlib

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

📂 Notebook

The full Jupyter Notebook includes:

Dataset loading

Obfuscation functions

Model generation

Metric computation

Visualization

Analysis
