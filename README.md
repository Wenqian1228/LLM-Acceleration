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

## Low-Rank Decomposition

## Others 

## Useful Toolchains

- [DeepSpeed](https://github.com/microsoft/DeepSpeed) : A deep learning optimization library including [DeepSpeed-Inference](https://www.deepspeed.ai/inference) and [DeepSpeed-Compression](https://www.deepspeed.ai/compression).

