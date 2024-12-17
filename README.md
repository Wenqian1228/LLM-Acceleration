# LLM-Acceleration
-----

## Table of Contents

*[Model Pruning](#model-pruning) 

*[Model Quantization](#model-quantization)

*[Low-Rank Decomposition](#low-rank-decomposition)

*[Others](#low-rank-decomposition)

*[Useful Toolchains](#useful-toolchains)

-----

## Model Pruning
- [SparseGPT: Massive Language Models Can Be Accurately Pruned in One-Shot](https://arxiv.org/abs/2301.00774) (**ICML**) 2023.
[[code]](https://github.com/IST-DASLab/sparsegpt) <br>
Post-training method for pruning LLMs in one-shot without any retraining. Updating weights by solving a layer-wise weight reconstruction problem. （Unstructured）

- [LLM-Pruner: On the Structural Pruning of Large Language Models](https://arxiv.org/abs/2305.11627) (**NeurIPS**) 2023.
[[code]](https://github.com/horseee/LLM-Pruner) <br>
First discover all coupled structures following Depgraph, then estimate grouped importance of coupled structure on calibration, then prune less important groups, and last finetune with efficient LoRA on Alpaca dataset consists of 50K instruction-response pairs.（Structured）



## Model Quantization

- [GPTQ: Accurate Post-Training Quantization for Generative Pre-trained Transformers](https://arxiv.org/abs/2210.17323) (**ICLR**) 2023.[[code]](https://github.com/IST-DASLab/gptq)
Elias Frantar, Saleh Ashkboos, Torsten Hoefler, Dan Alistarh
[[code]](https://github.com/IST-DASLab/gptq)


- [QServe: W4A8KV4 Quantization and System Co-design for Efficient LLM Serving](https://hanlab.mit.edu/projects/qserve) (**Arkiv**) 2024. [[code]](https://github.com/mit-han-lab/qserve)
Yujun Lin*, Haotian Tang*, Shang Yang*, Zhekai Zhang, Guangxuan Xiao, Chuang Gan, Song Han

- [AWQ: Activation-aware Weight Quantization for LLM Compression and Acceleration](https://arxiv.org/abs/2306.00978) (**MLSys**) 2025. 

## Low-Rank Decomposition

## Others 

## Useful Toolchains

- [DeepSpeed](https://github.com/microsoft/DeepSpeed) : A deep learning optimization library including [DeepSpeed-Inference](https://www.deepspeed.ai/inference) and [DeepSpeed-Compression](https://www.deepspeed.ai/compression).

