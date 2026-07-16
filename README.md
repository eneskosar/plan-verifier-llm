# Plan Verification in Natural Language with Large Language Models

Official implementation accompanying the paper:

> **Plan Verification in Natural Language:
A Logical Reasoning Framework for Large
Language Models**

## Overview

This repository contains the code used in the paper above for training and evaluating large language models on **plan verification in natural language**.

The proposed framework decomposes plan verification into three components:

- **Action Verifier:** a large language model that determines whether an action is executable in the current state.
- **State Updater:** a rule-based module generated from the planning domain that updates the current state after each executable action.
- **Goal Checker:** a rule-based module generated from the planning domain that determines whether the final state satisfies the goal conditions.

The key idea is to formulate **action verification as a logical reasoning task**. Rather than relying solely on domain-specific planning examples, the Action Verifier is trained using logical reasoning supervision together with a small number of domain-specific action verification examples.

---

## Repository Structure

The repository consists of Google Colab notebooks corresponding to different stages of the experimental pipeline.

| Notebook | Description |
|----------|-------------|
| `00_data_preparation.ipynb` | Prepare the training and evaluation datasets |
| `01a_train_stepwise_combined.ipynb` | Train the proposed stepwise Action Verifier |
| `01b_train_stepwise_ablations.ipynb` | Train the ablation models |
| `01c_train_direct_ft.ipynb` | Train the direct verification baseline |
| `02_eval_flant5.ipynb` | Evaluate FLAN-T5 models |
| `03_eval_gpt41mini.ipynb` | Evaluate GPT-4.1-mini |
| `04_eval_gpt5.ipynb` | Evaluate GPT-5 |
| `05_gpt5_results.ipynb` | Aggregate GPT-5 evaluation results |
| `06_unified_results.ipynb` | Generate the final experimental tables |
| `07_failing_plan_analysis.ipynb` | Analyze failure cases |

---

## Running the Experiments

The experiments are implemented as **Google Colab notebooks**. No local installation is required.

To reproduce the experiments:

1. Open the desired notebook in Google Colab.
2. Configure the required dataset locations and API keys (if applicable).
3. Execute the notebook cells sequentially.

The notebooks are intended to be executed in the following order:

1. `00_data_preparation.ipynb`
2. `01a_train_stepwise_combined.ipynb`
3. `01b_train_stepwise_ablations.ipynb`
4. `01c_train_direct_ft.ipynb`
5. `02_eval_flant5.ipynb`
6. `03_eval_gpt41mini.ipynb`
7. `04_eval_gpt5.ipynb`
8. `05_gpt5_results.ipynb`
9. `06_unified_results.ipynb`
10. `07_failing_plan_analysis.ipynb`

---

## Datasets

The experiments use:

- **FOLIO** for logical reasoning supervision.
- **PlanBench** for plan verification evaluation.

Please obtain these datasets from their official sources before running the notebooks.

---

## Requirements

The notebooks were developed using **Google Colab**.

Some notebooks additionally require:

- Hugging Face account (for downloading pretrained models and datasets)
- OpenAI API access (for GPT-4.1-mini and GPT-5 evaluations)

Please configure the required credentials before executing the corresponding notebooks.

---

## Citation

If you find this repository useful, please cite the accompanying paper.

```bibtex
@article{kosar2026planverification,
  title={Plan Verification in Natural Language: A Logical Reasoning Approach to Training Large Language Models},
  author={Ko\c{s}ar, Enes and Kozat, S{\"u}leyman Serdar},
  journal={Under Review},
  year={2026}
}
```

---


