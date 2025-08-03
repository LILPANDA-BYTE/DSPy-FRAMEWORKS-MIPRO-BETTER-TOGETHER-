\section*{DSPy Frameworks: MIPRO \& BetterTogether}

This repository demonstrates the power of the DSPy framework, focusing on two advanced optimizers: \textbf{MIPRO} (Multi-prompt Instruction PRoposal Optimizer) and \textbf{BetterTogether}. The project showcases how these powerful tools can be used to programmatically optimize Large Language Model (LLM) applications, moving beyond manual prompt engineering to create more reliable, efficient, and performant AI systems.

\subsection*{1. Introduction to DSPy}

DSPy (Declarative Self-improving Python) is a framework that allows you to build and optimize LLM applications by treating them as modular programs. Instead of ``prompt hacking,'' DSPy enables you to define the logical steps of your program, and then it uses optimizers (also known as \textit{teleprompters}) to automatically compile these programs into effective prompts or even fine-tuned weights for your chosen LLM. This approach makes your AI software more maintainable, reliable, and portable across different models and strategies.

\subsection*{2. Key Concepts}

The project explores two key DSPy optimizers:

\begin{itemize}
    \item \textbf{MIPROv2 (Multi-prompt Instruction PRoposal Optimizer v2)}: MIPRO is a sophisticated optimizer designed to improve the performance of LLM programs by jointly optimizing both natural language instructions and few-shot examples. It addresses the challenges of multi-stage programs and the credit assignment problem by:
    \begin{itemize}
        \item \textit{Bootstrapping Examples:} It generates candidate few-shot examples by running your program on a training dataset and keeping the successful runs.
        \item \textit{Proposing Instructions:} It proposes new, high-quality instructions for each module in your program by using the training data, code structure, and bootstrapped examples as context.
        \item \textit{Bayesian Optimization:} It then uses a search algorithm to find the best combination of instructions and examples for your program, optimizing for a specific metric.
    \end{itemize}
    
    \item \textbf{BetterTogether:} This experimental optimizer takes a powerful, multi-pronged approach to improving an LLM program's performance by alternating between prompt optimization and weight fine-tuning. This means it can first optimize the prompts of a program (e.g., using \texttt{BootstrapFewShotWithRandomSearch}) and then use the resulting data to fine-tune the LLM's weights (\texttt{BootstrapFinetune}), leading to a more robust and highly optimized model.
\end{itemize}

\subsection*{3. Installation}

To get started with this project, you need to install the \texttt{dspy} framework and any other dependencies.

\begin{enumerate}
    \item Clone this repository:
    \begin{verbatim}
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
    \end{verbatim}
    
    \item Install DSPy and other necessary libraries:
    \begin{verbatim}
pip install -U dspy
    \end{verbatim}
    
    \item Configure your Large Language Model (LLM) provider. DSPy supports various providers, including OpenAI, Anthropic, Databricks, and local models via \texttt{LiteLLM}. Set your API key as an environment variable or configure it in the code:
    \begin{verbatim}
import dspy
lm = dspy.OpenAI(model='gpt-4o-mini', api_key='YOUR_API_KEY')
dspy.settings.configure(lm=lm)
    \end{verbatim}
\end{enumerate}

\subsection*{4. Usage}

This repository contains a Jupyter notebook that demonstrates how to implement and use the MIPRO and BetterTogether optimizers.

\begin{enumerate}
    \item Open the Jupyter notebook:
    \begin{verbatim}
jupyter notebook "DSPy FRAMEWORKS (MIPRO & BETTER TOGETHER) .ipynb"
    \end{verbatim}
    
    \item Follow the steps in the notebook, which will likely include:
    \begin{itemize}
        \item Defining your task using a \texttt{dspy.Signature}.
        \item Creating a multi-module DSPy program.
        \item Defining a metric function to evaluate the program's performance.
        \item Initializing and compiling the program with \texttt{dspy.teleprompt.MIPROv2} and \texttt{dspy.teleprompt.BetterTogether}.
    \end{itemize}
\end{enumerate}

\subsection*{5. Contributing}

Contributions are welcome! If you have any suggestions, bug reports, or feature requests, please open an issue or submit a pull request.

\subsection*{6. License}

This project is open-source. See the \texttt{LICENSE} file for details.


