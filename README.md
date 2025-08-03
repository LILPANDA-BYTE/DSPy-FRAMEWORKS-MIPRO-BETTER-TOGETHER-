# DSPy Frameworks: MIPRO & BetterTogether

This repository demonstrates the power of the **DSPy framework**, focusing on two advanced optimizers: **MIPRO** (Multi-prompt Instruction PRoposal Optimizer) and **BetterTogether**. The project showcases how these powerful tools can be used to programmatically optimize Large Language Model (LLM) applications, moving beyond manual prompt engineering to create more reliable, efficient, and performant AI systems.

---

## 📌 1. Introduction to DSPy

**DSPy (Declarative Self-improving Python)** is a framework that allows you to build and optimize LLM applications by treating them as modular programs.

Instead of traditional *prompt hacking*, DSPy enables you to define the logical steps of your program. Then, it uses **optimizers (teleprompters)** to automatically compile these programs into effective prompts or even fine-tuned weights for your chosen LLM.

This approach makes your AI software:

* More **maintainable**
* More **reliable**
* More **portable** across different models and strategies

---

## ⚙️ 2. Key Concepts

This project explores two key DSPy optimizers:

### 🔹 MIPROv2 (Multi-prompt Instruction PRoposal Optimizer v2)

MIPRO is a sophisticated optimizer that jointly optimizes:

* Natural language instructions
* Few-shot examples

It addresses multi-stage programs and credit assignment problems by:

* **Bootstrapping Examples:** Runs your program on a training set, collecting successful examples.
* **Proposing Instructions:** Proposes new, high-quality instructions for each module using training data and the code structure.
* **Bayesian Optimization:** Finds the best combination of instructions and examples that optimize a specified metric.

---

### 🔹 BetterTogether

BetterTogether is an **experimental optimizer** that improves program performance by alternating between:

* Prompt optimization (e.g., `BootstrapFewShotWithRandomSearch`)
* Weight fine-tuning (`BootstrapFinetune`)

This dual-phase approach results in:

* More robust programs
* Highly optimized model performance

---

## 📥 3. Installation

To get started:

### Step 1: Clone the repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### Step 2: Install dependencies

```bash
pip install -U dspy
```

### Step 3: Configure your LLM provider

DSPy supports OpenAI, Anthropic, Databricks, and local models via `LiteLLM`.

```python
import dspy

lm = dspy.OpenAI(model='gpt-4o-mini', api_key='YOUR_API_KEY')
dspy.settings.configure(lm=lm)
```

---

## 🧪 4. Usage

This repo contains a Jupyter notebook that demonstrates using **MIPRO** and **BetterTogether**.

### Open the notebook:

```bash
jupyter notebook "DSPy FRAMEWORKS (MIPRO & BETTER TOGETHER).ipynb"
```

### Follow the steps to:

* Define tasks with `dspy.Signature`
* Create a multi-module DSPy program
* Write an evaluation metric
* Compile the program using:

  * `dspy.teleprompt.MIPROv2`
  * `dspy.teleprompt.BetterTogether`

---

## 🤝 5. Contributing

Contributions are welcome!

* Found a bug? Open an [issue](https://github.com/your-username/your-repo-name/issues)
* Have a feature idea? Submit a [pull request](https://github.com/your-username/your-repo-name/pulls)

---

## 📝 6. License

This project is open-source. See the [`LICENSE`](./LICENSE) file for more details.

---


