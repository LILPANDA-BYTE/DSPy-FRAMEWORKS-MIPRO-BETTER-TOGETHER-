## DSPy Frameworks: MIPRO & BETTER TOGETHER

This repository contains a Jupyter notebook demonstrating the application of **DSPy**, a framework designed to optimize prompts and weights in language model pipelines. The notebook, titled **"DSPy FRAMEWORKS (MIPRO & BETTER TOGETHER) .ipynb"**, focuses on two specific techniques within DSPy—**MIPRO** and **BETTER TOGETHER**—and applies them to solve a dataset of math word problems.

---

### Introduction

The primary purpose of this repository is to showcase how DSPy can be used to enhance the performance of language models in solving mathematical word problems. The notebook:

1. Processes a series of prompts (math word problems).
2. Generates responses using a DSPy-optimized model.
3. Compares these responses to ground truth answers.
4. Tracks the model's accuracy over time.

By the end, you will see how MIPRO and BETTER TOGETHER methods improve the accuracy of generated solutions.

---

### Dataset

* Total Problems Evaluated: **1,125** math word problems
* Ground Truth Answers: Numerical values
* Topics Covered:

  * Basic arithmetic (addition, subtraction, multiplication, division)
  * Percentages and proportions
  * Rates and ratios
  * Algebraic reasoning
  * Multi-step problem-solving

**Example Prompts:**

* "Ted starts with \$200. He buys 3 books for 16 dollars each and 3 pencils for 6 dollars each. How much did he spend in total?" (Ground Truth: 66)
* "Ingrid drinks 8 cups of water every day. If there are 16 cups in a gallon, how many gallons of water does she drink in 30 days?" (Ground Truth: 15)

> *Note:* The dataset appears to be a subset of a larger collection (7,473 examples), but this notebook specifically processes 1,125 problems for evaluation.

---

### Methodology

#### DSPy Overview

DSPy is a Python framework that automates the optimization of language model pipelines by refining prompts and adjusting model weights. Unlike manual prompt engineering, DSPy provides a systematic, reproducible process for identifying optimal prompt structures.

#### MIPRO Technique

**MIPRO** (Multi-Instruction Prompt Optimization) explores multiple prompt variations to find the most effective phrasing for a given task. In this notebook, MIPRO optimizes math word problem prompts to maximize the likelihood of correct answers.

#### BETTER TOGETHER Technique

**BETTER TOGETHER** involves combining multiple models or optimization strategies to outperform a single approach. Possible implementations include:

* **Ensemble Methods:** Aggregating predictions from multiple DSPy-optimized models.
* **Layered Optimization:** Applying MIPRO-optimized prompts followed by additional DSPy refinements.

Together, MIPRO and BETTER TOGETHER generate responses and evaluate correctness against ground truth values.

---

### Implementation Details

The notebook includes code cells that:

1. **Load and Preprocess** the dataset of math word problems.
2. **Configure DSPy** with MIPRO and BETTER TOGETHER.
3. **Generate Responses** for each prompt using the optimized model.
4. **Compare Responses** to ground truth and update a correctness counter.

**Sample Output Log:**

```
Prompt: Ted starts with $200. He buys 3 books for 16 dollars each and 3 pencils for 6 dollars each. How much did he spend in total?
Response: $66
Ground Truth: 66
correct so far: 791.0
dataset: 1035
```

---

### Results

By the final problem (index 1125), the model correctly answered **856** questions, yielding an accuracy of:

```
Accuracy = (856 / 1125) * 100 ≈ 76.09%
```

**Key Observations:**

* Strong performance on straightforward arithmetic and rate problems.
* Challenges with complex multi-step or probabilistic reasoning.
* DSPy optimizations significantly boost performance, though further refinements could improve accuracy.

---

### How to Run the Notebook

To get the notebook up and running, follow these structured steps:

#### 1. Clone & Navigate

```bash
# Clone the repository
git clone <repository-url>
cd <repository-directory>
```

#### 2. (Optional) Create a Virtual Environment

```bash
# macOS/Linux
python3 -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
venv\Scripts\activate
```

#### 3. Install Dependencies

> **If** there is a `requirements.txt` in the repo:

```bash
pip install -r requirements.txt
```

> **Otherwise** manually install:

```bash
pip install dspy-ai numpy pandas jupyter
```

#### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

* In your browser, open: `DSPy FRAMEWORKS (MIPRO & BETTER TOGETHER) .ipynb`
* Run all cells in order: select a cell and press **Shift + Enter**.

#### 5. Verify Dataset Path

* Ensure `train-00000-of-00001.parquet` is located alongside the notebook, or update the file path in the first code cell to point to its correct location.

\$1

For each problem, the notebook logs:

* **Prompt:** Math word problem text
* **Response:** Model's generated answer
* **Ground Truth:** Correct answer
* **Correct So Far:** Running count of correct responses
* **Dataset Index:** Problem number (1–1125)

Monitor **“correct so far”** to assess performance trajectory.

---

### Conclusion & Future Work

This repository demonstrates how DSPy’s MIPRO and BETTER TOGETHER techniques achieve a **76.09%** accuracy on a challenging math word problem dataset. Future improvements include:

* Fine-tuning MIPRO prompt variations for specific problem types.
* Exploring additional DSPy techniques to boost accuracy.
* Expanding the dataset with more diverse problem categories.

Feel free to explore the notebook, replicate the results, or adapt the code for your own datasets and tasks!

