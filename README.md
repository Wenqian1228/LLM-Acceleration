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
- [SparseGPT: Massive Language Models Can Be Accurately Pruned in One-Shot](https://arxiv.org/abs/2301.00774) (**ICML**) 2023. <br>
Elias Frantar, Dan Alistarh <br>
Post-training method for pruning LLMs in one-shot without any retraining. Updating weights by solving a layer-wise weight reconstruction problem. （Unstructured）<br>
[[code]](https://github.com/IST-DASLab/sparsegpt)

- [LLM-Pruner: On the Structural Pruning of Large Language Models](https://arxiv.org/abs/2305.11627) (**NeurIPS**) 2023. <br>
Xinyin Ma, Gongfan Fang, Xinchao Wang* <br>
First discover all coupled structures following Depgraph, then estimate grouped importance of coupled structure on calibration, then prune less important groups, and last finetune with efficient LoRA on Alpaca dataset consists of 50K instruction-response pairs.（Structured）<br>
[[code]](https://github.com/horseee/LLM-Pruner) 

- [SliceGPT: Compress Large Language Models by Deleting Rows and Columns](https://arxiv.org/abs/2401.15024) (**ICLR**) 2024. <br>
Saleh Ashkboos*, Maximilian L. Croci*, Marcelo Gennari do Nascimento, Torsten Hoefler, James Hensman <br>
A post-training sparsification scheme that makes transformer networks (including LLMs) smaller by first applying orthogonal transformations to each transformer layer that leave the model unchanged, and then slicing off the least-significant rows and columns (chosen by the eigenvalue decay) of the weight matrices. The model structure is left unchanged, but each weight matrix is replaced by a smaller (dense) weight matrix, reducing the embedding dimension of the model. (Structured) <br>
[[code]](https://github.com/microsoft/TransformerCompression)

- [Sheared LLaMA: Accelerating Language Model Pre-training via Structured Pruning](https://arxiv.org/abs/2310.06694) (**ICLR**) 2024. <br>
Mengzhou Xia, Tianyu Gao, Zhiyuan Zeng, Danqi Chen <br>
In first stage, training-aware pruning learns masks satisfying specified target by imposing regularization on ~0.4B tokens; then retrain on other ~5B tokens of RedPajama dataset. Dynamic batch loading method to update the composition of sampled data per mini-batch across different domains. (Structured) <br>
[[code]](https://github.com/princeton-nlp/LLM-Shearing)

- [Compact Language Models via Pruning and Knowledge Distillation](https://arxiv.org/abs/2407.14679) (**arXiv**) 2024. <br>
Saurav Muralidharan*, Sharath Turuvekere Sreenivas*, Raviraj Joshi, Marcin Chochowski, Mostofa Patwary, Mohammad Shoeybi, Bryan Catanzaro, Jan Kautz, Pavlo Molchanov <br>
Prune LLMs structurally along different axes such as layer, neuron, head, and embedding channel, similar to NAS that searches over different dimensions. Difference lies in the defined search space that for pruning a pre-trained large model as search space (simpler) while NAS searches over a manually-pre-defined search space (more complex) from scratch. Different proxy importance scores are estimated for depth and width pruning. Retraining with knowledge distillation requires up to 40x fewer training tokens. (Structured + distillation) <br>
[[code]](https://github.com/NVlabs/Minitron)

- [Shortened LLaMA: A Simple Depth Pruning for Large Language Models](https://arxiv.org/abs/2402.02834) (**ICLR Workshop**) 2024. <br>
Bo-Kyeong Kim*, Geonmin Kim*, Tae-Ho Kim, Thibault Castells, Shinkook Choi, Junho Shin, Hyoung-Kyu Song <br>
First identify unimportant Transformer blocks (bigger and coarse units), then perform one-shot pruning with Perplexity (PPL) as pruning criteria and light LoRA retraining. Show fast inference and good zero-shot capabilities. (Structured) <br>
[[code]](https://github.com/Nota-NetsPresso/shortened-llm)

## Model Quantization

- [GPTQ: Accurate Post-Training Quantization for Generative Pre-trained Transformers](https://arxiv.org/abs/2210.17323) (**ICLR**) 2023. <br>
Elias Frantar, Saleh Ashkboos, Torsten Hoefler, Dan Alistarh <br>
[[code]](https://github.com/IST-DASLab/gptq)

- [QServe: W4A8KV4 Quantization and System Co-design for Efficient LLM Serving](https://hanlab.mit.edu/projects/qserve) (**Arkiv**) 2024. <br>
Yujun Lin*, Haotian Tang*, Shang Yang*, Zhekai Zhang, Guangxuan Xiao, Chuang Gan, Song Han <br>
[[code]](https://github.com/mit-han-lab/qserve)

- [AWQ: Activation-aware Weight Quantization for LLM Compression and Acceleration](https://arxiv.org/abs/2306.00978) (**MLSys**) 2025. <br>
Ji Lin, Jiaming Tang, Haotian Tang, Shang Yang, Wei-Ming Chen, Wei-Chen Wang, Guangxuan Xiao, Xingyu Dang, Chuang Gan, Song Han <br>
[[code]](https://github.com/mit-han-lab/llm-awq)

- [SmoothQuant: Accurate and Efficient Post-Training Quantization for Large Language Models](https://arxiv.org/abs/2211.10438) (**ICML**) 2023. <br>
Guangxuan Xiao, Ji Lin, Mickael Seznec, Hao Wu, Julien Demouth, Song Han <br>
[[code]](https://github.com/mit-han-lab/smoothquant) 

- [SqueezeLLM: Dense-and-Sparse Quantization](https://arxiv.org/abs/2306.07629) (**ICML**) 2024. <br>
Sehoon Kim, Coleman Richard Charles Hooper, Amir Gholami, Zhen Dong, Xiuyu Li, Sheng Shen, Michael W. Mahoney, Kurt Keutzer <br>
[[code]](https://github.com/SqueezeAILab/SqueezeLLM)

- [COAT: Compressing Optimizer States and Activation for Memory-Efficient FP8 Training](https://arxiv.org/abs/2410.19313) (**Arkiv**) 2024. <br>
Haocheng Xi, Han Cai, Ligeng Zhu, Yao Lu, Kurt Keutzer, Jianfei Chen, Song Han <br>
[[code]](https://github.com/NVlabs/COAT?tab=readme-ov-file)

- [KVQuant: Towards 10 Million Context Length LLM Inference with KV Cache Quantization](https://arxiv.org/abs/2401.18079) (**NIPS**) 2024. <br>
Coleman Hooper, Sehoon Kim, Hiva Mohammadzadeh, Michael W. Mahoney, Yakun Sophia Shao, Kurt Keutzer, Amir Gholami <br>
[[code]](https://github.com/SqueezeAILab/KVQuant)







## Low-Rank Decomposition

- [SVD-LLM: Truncation-aware Singular Value Decomposition for Large Language Model Compression](https://arxiv.org/abs/2403.07378) (**Arxiv**) 2024. <br>
Xin Wang, Yu Zheng, Zhongwei Wan, Mi Zhang <br>
[[code]](https://github.com/AIoT-MLSys-Lab/SVD-LLM)

## Others 
- [Computational Bottlenecks of Training Small-scale Large Language Models](https://arxiv.org/abs/2410.19456) (**Arkiv**) 2024. <br>
Saleh Ashkboos, Iman Mirzadeh, Keivan Alizadeh, Mohammad Hossein Sekhavat, Moin Nabi, Mehrdad Farajtabar, Fartash Faghri <br>

- [LLMCompiler: An LLM Compiler for Parallel Function Calling](https://github.com/SqueezeAILab/LLMCompiler) (**ICML**) 2024. <br>
Sehoon Kim, Suhong Moon, Ryan Tabrizi, Nicholas Lee, Michael W. Mahoney, Kurt Keutzer, Amir Gholami <br>
[[code]](https://github.com/SqueezeAILab/LLMCompiler?tab=readme-ov-file)

## Useful Toolchains

- [DeepSpeed](https://github.com/microsoft/DeepSpeed) : A deep learning optimization library including [DeepSpeed-Inference](https://www.deepspeed.ai/inference) and [DeepSpeed-Compression](https://www.deepspeed.ai/compression).

