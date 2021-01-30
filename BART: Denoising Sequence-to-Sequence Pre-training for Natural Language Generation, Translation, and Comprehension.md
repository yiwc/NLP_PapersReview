#Title:
BART: Denoising Sequence-to-Sequence Pre-training for Natural Language Generation,
Translation, and Comprehension

#Task tackled:
What is the best data preprocessing methods (noising approaches) for training.

#Main novel Ideas:
It gives corrupted and reconstruct method in the pretraining.

#Overview of Method
##1. Architecture:
a) Decoder additionally performs cross-attention over final hidden layer
b) Roughly 10% more parameters than BERT
##2. Pre-training: Two stage pretraining:
a) Corruption:: Text is corrupted with an arbitrary noising function
i. Token Masking: like BERT
ii. Token Deletion: random tokens are deleted.
iii. Text Infilling: Random number (Poisson Distribution) of words are masked.
iv. Sentence Permutation: Full stops sentences are shuffled.
v. Document Rotation: Identify the start of document with rotated document.
b) Reconstruction: a seq2seq model is learned to reconstruct the original text
##3. Fine-Tuning BART:
a) Sequence Classfication Tasks
b) Token Classfications Tasks
c) Seq Generation
d) Machine Translation

#Evaluation:
##1. Benchmark Models: Compared with those recent models: Language Model, Permuted
Language Model, Masked Language Model, Multitask Masked Language Model, Masked
Seq-to-Seq
##2. Tasks: SquAD, MNLI, ELI5, XSum, ConvAI2, CNNDM
##3. Results:
a) Performance of pre-training methods varies significantly across tasks.
b) Token masking is crucial
c) Left-to-rhight pretraining improves generation
d) Biderectional Encoders are crucial for SquAD
e) The pretraining objective is not the only important factor.
f) Pure language models perform best on ELI5.
##4. Large-scale Pretraining Experiments: Large model with 12 layers in each of encoder and
decoder with a hidden size of 1024.
a) Discriminative Tasks: Overall, BART performs similarly to RoBERTa.
b) Generation Tasks:
i. Summarization tasks: BART significantly outperforms the prior works
ii. Dialogue tasks: BART outperforms partially
iii. Abstractive QA: BART is the SOTA

#Critique/limitation:
1. There is a tendency to hallucinate unsupported informantion.
2. Generally, BART is updated version of BERT with Corruption mask and reconstruction
pre-training. There still no major update from the original model.

#Suggestions for extensions:
1. There can be more data corruption methods can be investigated. Like using random
mask under different distribution (currently using Possion mask in Text Infilling.), or
trying dynamic adaptive random masking (random seed changes dynamically with
training performance)


# 中文版 (Google Translation)
＃标题：
BART：自然语言生成的序列到序列预训练降噪，
翻译与理解
＃任务解决：
什么是训练的最佳数据预处理方法（降噪方法）。
＃主要新颖创意：
它给出了预训练中损坏和重建的方法。
＃方法概述
## 1。建筑：
a）解码器还对最终隐藏层执行交叉注意
b）比BERT多大约10％的参数
## 2。预培训：两阶段预培训：
a）损坏：：文本被任意的提示功能损坏
一世。令牌屏蔽：像BERT
ii。令牌删除：随机令牌被删除。
iii。文本填充：单词的随机数（泊松分布）被屏蔽。
iv。句子排列：句点被打乱。
v。文件旋转：标识旋转文件的开始。
b）重建：学习seq2seq模型以重建原始文本
## 3。微调BART：
a）序列分类任务
b）令牌分类任务
c）序列生成
d）机器翻译
＃评估：
## 1。基准模型：与最近的模型比较：语言模型，置换
语言模型，屏蔽语言模型，多任务屏蔽语言模型，屏蔽
序列到序列
## 2。任务：SquAD，MNLI，ELI5，XSum，ConvAI2，CNNDM
## 3。结果：
a）预培训方法的性能因任务而异。
b）令牌屏蔽至关重要
c）从左至高的预训练可提高生成能力
d）双向编码器对于SquAD至关重要
e）培训的目标不是唯一重要的因素。
f）纯语言模型在ELI5上表现最佳。
## 4。大规模的预训练实验：编码器和
隐藏大小为1024的解码器。
a）区分性任务：总体而言，BART的表现与RoBERTa相似。
b）生成任务：
一世。总结任务：BART明显优于先前的工作
ii。对话任务：BART部分胜过
iii。抽象质量检查：BART是SOTA
＃评论/限制：
1.倾向于使无根据的信息产生幻觉。
2.通常，BART是BERT的更新版本，其中包含腐败掩码和重建功能
预训练。原始模型仍然没有重大更新。
＃扩展建议：
1.可以研究更多的数据损坏方法。喜欢使用随机
分布不同的蒙版（当前使用“文本填充”中的“位置蒙版”），或
尝试动态自适应随机掩蔽（随机种子随
训练表现）