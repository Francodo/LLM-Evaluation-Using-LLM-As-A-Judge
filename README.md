Project: Automated LLM Evaluation Framework (LLM-as-a-Judge)


Overview

This application implements a rigorous LLM-as-a-Judge architecture designed to automate the evaluation of Large Language Model (LLM) outputs. By moving away from manual "vibes-based" review, this framework leverages high-reasoning models—such as Gemini 1.5 Pro or Claude 3.5 Sonnet—to programmatically assess the accuracy and correctness of a Source LLM's responses.
Core Methodology

The experiment utilizes the EvidentlyAI SDK to facilitate a structured evaluation pipeline. Using a Binary Classification Prompt Template, the "Judge LLM" compares a candidate response against a labeled "Ground Truth" dataset to assign a definitive CORRECT or INCORRECT label.
Technical Workflow

    Reference Alignment: The system ingests a labeled dataset consisting of predefined Questions (target_response) and model-generated outputs (new_response).

    Binary Evaluation: The Judge LLM performs a semantic audit, classifying the response based on factual alignment and instruction-following.

    Reasoning Attribution: Beyond a simple label, the judge generates a Correctness_Reasoning field, providing transparency into the logic behind the judgment.

    Metric Visualization: Utilizing the ColumnDistributionMetric, the application generates a visual distribution report (Count Graph) to analyze performance trends across the dataset.

    Downstream Integration: The final evaluation report is exportable as a structured JSON/Dictionary, enabling seamless ingestion into monitoring dashboards or MLOps pipelines.

Evaluation Schema

Every evaluation record consists of the following data points:

    Question: The original input prompt.

    Target Response: The expected "Golden" answer (Ground Truth).

    New Response: The actual output from the Source LLM under test.

    Label: Binary classification (CORRECT / INCORRECT).

    Correctness & Reasoning: A detailed qualitative analysis of the judge's decision.
