##Title:
RoBERTa: A Robustly Optimized BERT Pretraining Approach
##Task tackled:
How to better train BERR model, what useful tricks needed.
##Main novel Ideas:
It gives following training tricks:
1. Dynamic Masking,
2. Removing NSP loss
3. Larger Batchsize
4. Bigger text-encoding universe (trade-off performance)
5. Additional Datasets and longer training
##Advances (better in what ways):
It gives those tricks that BERT basic model didn’t noticed. And those tricks can lead to
performance improving.
##Overview of Method
RoBERTa, Robustly Optimized BERT Approach, uses dynamic masking, FULL-SENTENCES
without NSP loss, large batch size, and a larger byte-level BPE.
1. Dynamic Masking : slightly better than static mask or similar.
2. With or without NSP loss:
a) If with NSP loss: Segments sentences are better than individual sentences.
b) If No NSP Loss: generally better than with NSP loss.
3. Large Batches: 2K bs is better than 256 bs, while 8K bs is worse than 2K bs.
4. Text Encoding: BPE with larger vocabulary shows worse result. But we can have a bigger
universe.
5. Additional Datasets: additional datasets gives better performance. Bench mark datasets
are BOOKS+WIKI, and the additional datasets are CC-NEWS, OEPNWEBTEXT, STORIES.
##Evaluation:
Evaluation is performed on GLUE, SQUAD and RACE
a) GLUE: shows SOTA result on all 9 tasks of GLUE.
b) SQuAD:shows SOTA result on SquAD without additional data.
c) RACE: shows SOTA results both in middle-school and high-school settings.
##Critique/limitation:
1. It doesn’t give major update or redesign of the BERT model, it focus on the training tricks.
This results only shows a minor performance improving.
2. It shows plentiful experiments and those results are convinced.
##Suggestions for extensions:
1. Masking methods can be further explored. Currently no matter the static mask and the
dynamics masking, both of the masking methods are based upon random masking. A
further data preprocessing like corrupting can be investigated

# 中文版 (Google Translation)
＃＃标题：
RoBERTa：鲁棒优化的BERT预训练方法
##解决的任务：
如何更好地训练BERR模型，需要哪些有用的技巧。
##主要小说创意：
它提供以下训练技巧：
1.动态遮罩
2.消除NSP损失
3.更大的批量
4.更大的文本编码范围（权衡性能）
5.附加数据集和更长的培训
## Advances（更好的方式）：
它提供了BERT基本模型没有注意到的那些技巧。这些技巧可能导致
性能提高。
##方法概述
RoBERTa，经过稳健优化的BERT方法，使用动态掩膜，全图
没有NSP损失，大批处理大小和更大的字节级BPE。
1.动态遮罩：比静态遮罩或类似遮罩略好。
2.有无NSP损失：
a）如果NSP丢失：段句比单个句更好。
b）如果没有NSP损失：通常要好于NSP损失。
3.大批量：2K bs优于256 bs，而8K bs则比2K bs差。
4.文本编码：词汇量较大的BPE显示较差的结果。但是我们可以拥有更大的
宇宙。
5.其他数据集：其他数据集可提供更好的性能。基准数据集
是BOOKS + WIKI，其他数据集是CC-NEWS，OEPNWEBTEXT和STORIES。
##评估：
对GLUE，SQUAD和RACE进行评估
a）GLUE：显示GLUE的所有9个任务的SOTA结果。
b）SQuAD：显示SquAD上的SOTA结果，而没有其他数据。
c）种族：显示中学和高中环境中的SOTA结果。
##评论/限制：
1.它没有对BERT模型进行重大更新或重新设计，而是着重于训练技巧。
此结果仅显示次要性能的提高。
2.它显示了大量的实验，并且这些结果令人信服。
##扩展建议：
1.掩膜方法可以进一步探索。目前无论是静态蒙版还是
动态遮罩，这两种遮罩方法都是基于随机遮罩。一个
可以研究进一步的数据预处理，例如损坏