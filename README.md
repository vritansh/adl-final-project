# Mental Health Chat Bot Readme

Report is accessible here : [https://docs.google.com/document/d/1-_UrFEylkIIsJ3JS4Fiv9_nquD0LjlEzGezDqQX1Cjk/edit?usp=sharing](https://drive.google.com/file/d/1OwuZ_6XY4B8sf_DkZdnPpLak0vU-7M2K/view?usp=sharing)

The goal of this project is to develop a prototype for the fine-tuning of the Falcon 7 billion LLM (Large Language Model) using a dataset focused on mental health conversations. The project utilizes LORA ( Low Rank Adaptation )  for fine-tuning the LLM, employing the Hugging Face Supervised Fine Tuning approach. Techniques such as Parameter Efficient Fine Tuning (PEFT) are incorporated.

**Note:** Results in the notebook may vary from those in the report.

## Model Used
- **Model:** [Falcon-7B-Instruct](https://huggingface.co/tiiuae/falcon-7b-instruct)
- **Dataset:** [Mental Health Counseling Conversations](https://huggingface.co/datasets/Amod/mental_health_counseling_conversations)

The model was trained using the Hugging Face LORA & PEFT libraries.

### Model Configuration

| Configuration / Training                   | Value                                                |
| ------------------------------------------- | ---------------------------------------------------- |
| r                                           | 8                                                    |
| lora_alpha                                  | 32                                                   |
| LORA Modules                               | ['query_key_value', 'dense', 'dense_h_to_4h', 'dense_4h_to_h'] |
| lora_dropout                                | 0.05                                                 |
| bias                                        | "none"                                               |
| per_device_train_batch_size                 | 16                                                   |
| gradient_accumulation_steps                 | 16                                                   |
| save_steps                                  | 100                                                  |
| learning_rate                               | 0.001                                               |
| max_grad_norm                               | 0.3 (maximum gradient norm for gradient clipping)    |
| max_steps                                   | 600                                                  |
| warmup_ratio                                | 0.03 (number of steps for linear warmup)             |
| sequence_length                             | 1024                                                 |
| maximum steps                               | 600                                                 |
| Training Time                               | 6 hours                                             |

Fine-tuned model is available at: [Falcon 7B Mental Health LORA](https://huggingface.co/vkamal/falcon_7b_instruct_trained_mental_health_lora)

Results available at: [WandB - Fine Tuner](https://api.wandb.ai/links/fine-tuner/y4nxzle7)
