# LLM_Automatic-evaluation
This repository provides a complete workflow for evaluating Large Language Model (LLM) responses using both automatic metrics (BLEU, ROUGE-L, BERT) and AI-based judgment. The pipeline supports comparing model responses to reference answers and applies machine learning for automated correctness prediction.
| File                                       | Description                                                                                                                                                                                                                                                                                                                                              |
| ------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **`Response from_Claude_MD.ipynb`**        | Example notebook showing how to obtain responses from an LLM (e.g., Claude) for uploaded questions. It supports two modes:<br>• **NSD (Non-prompted mode)** – responses generated without additional prompts.<br>• **IAQ (Prompted mode)** – responses generated with a guiding prompt.                                                                  |
| **`Conceptual Comparision metrics.ipynb`** | Compares LLM model responses with reference answers using the following metrics:<br>• **BLEU** – measures n-gram overlap.<br>• **ROUGE-L** – measures longest common subsequence similarity.<br>• **BERTScore** – measures semantic similarity using contextual embeddings.                                                                              |
| **`Four_metrics.ipynb`**                   | Extends evaluation by adding a **fourth metric: AI judgment**. This uses an LLM to assess whether a response is correct based on reasoning and conceptual understanding, complementing BLEU, ROUGE-L, and BERTScore.                                                                                                      |
| **`Automatic_evaluation.ipynb`**           | Integrates all four metrics (BLEU, ROUGE-L, BERTScore, and AI judgment) into a **machine learning model** for automated evaluation. Uses:<br>• **LightGBM** as the classifier.<br>• **SMOTEENN** for class imbalance correction.<br>The model outputs a **binary prediction**:<br>• `1` → LLM response is correct.<br>• `0` → LLM response is incorrect. |

Workflow Summary

1.Generate Responses
Use Response from_Claude_MD.ipynb to obtain model-generated answers (NSD and IAQ modes).

2.Compute Metrics
Run Conceptual Comparision metrics.ipynb to calculate BLEU, ROUGE-L, and BERTScore.

3.Add AI Judgment
Use Four_metrics.ipynb to include AI-based correctness assessment as the fourth metric.

4.Automatic Evaluation
Execute Automatic_evaluation.ipynb to train and test a LightGBM model (with SMOTEENN) that predicts whether an LLM response is correct or not.
