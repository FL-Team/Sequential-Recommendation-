# RP-SANRec 
+ Research Direction：Sequential Recommendation 
+ Quote: X. Zheng, X. Li, et al., "Enhanced Self-Attention Mechanism for Long and Short Term Sequential Recommendation Models," in IEEE Transactions on Emerging Topics in Computational Intelligence, vol. 8, no. 3, pp. 2457-2466, June 2024, doi: 10.1109/TETCI.2024.3366771.
+ Link: https://ieeexplore.ieee.org/abstract/document/10445350

## 模型介绍

### 1、Abstract
Compared with traditional recommendation algorithms based on collaborative filtering and content, sequence recommendation can better capture changes in user interests and recommend items that may be interacted with next time according to the user's historical interaction behavior. There are two traditional methods for sequence recommendation: Markov Chain (MC) and Recurrent Neural Network (RNN), both of which ignore the relationship between various behaviors and the dynamic change of user interest in items over time. In addition, previous studies usually deal with users' long-term continuous behavior in a left-to-right order, which may ignore some useful information in the overall preferences of users. In this paper, we propose a new long-term and short-term sequence recommendation model with enhanced self-attention network named RP-SANRec. The model first divides the user historical interaction sequence into multiple subsequences according to the time span. The short-term interest module of the model uses the gated recurrent unit (GRU) to train the user's entire historical interaction sequence to obtain its position weight information in time order, and use this weight to enhance the input of the self-attention mechanism, and then obtain the user's short-term. The long-term interest module captures the user's overall preference through a bidirectional long-short-term memory network (Bi-LSTM). Finally, the long-term and short-term interest preferences are fused and output, and the next recommendation result is obtained. In this paper, the RP-SANRec model is applied to three different data sets, using HR@10 and NDCG@10 two evaluation indicators. Through a large number of experiments, it is proved that the RP-SANRec model is better than the existing models. 

与基于协同过滤和基于内容的传统推荐算法相比，序列推荐能够更好的捕捉用户兴趣变化，根据用户的历史交互行为向用户推荐下一次可能交互的物品。序列推荐的传统方法主要有两种方法马尔科夫链（MC）和循环神经网络（RNN），两者都忽略了各个行为之间的关系以及用户对项目的兴趣度随着时间推进而动态变化的问题。另外，以往的研究通常是按照从左到右的顺序来处理用户的长期连续行为，这种处理方式可能会忽略一些用户整体偏好中有用的信息。本文提出了一种新的增强自注意力网络的长短期序列推荐模型RP-SANRec。该模型首先根据时间跨度将用户历史交互序列划分成多个子序列。模型的短期兴趣模块利用门控循环单元（GRU）对用户的整个历史交互序列进行训练得到其关于时间顺序上的位置权重信息，以该权重去增强自注意力机制的输入，进而得到用户的短期兴趣表示。长期兴趣模块通过双向长短时记忆网络（Bi-LSTM）捕捉用户的整体偏好。最终将长短期兴趣偏好融合输出，得到下一项推荐结果。本文将RP-SANRec模型应用在3个不同的数据集上，采用HR@10和NDCG@10两种评价指标，通过大量的实验证明，RP-SANRec模型优于目前已存在的模型。 

### 2、模型图示
![image](https://github.com/FL-Team/TeamWork-Recommendation/assets/171318468/390575b8-85c1-4584-9e60-92819bccb294)

### 3、创新点
1. RP-SANRec模型采用GRU门控循环单元改良自注意力机制，并对用户的历史交互序列进行建模，使得模型可以自动地关注到每个动作的局部位置特征，增强了模型捕获用户短期兴趣动态变化特征的能力。
2. 本文提出了一个新的长短期序列推荐模型，该模型分别通过增强自注意力机制和特征聚合的Bi-LSTM网络捕获用户长短期行为中的相关性，改善了传统模型在局部以及全局模式下的学习能力，提高了序列推荐的准确性。
3. 在三个常用的公开数据集上测试本文模型，经多次实验结果表明本文提出的RP-SANRec模型在下一项推荐的效果高于其他方法，可以获得较好的性能提升。


## 编译环境
+ python: 3.6.13
+ tensorflow: 2.5.0
+ tensorflow-gpu: 2.3.0
+ pytorch: 1.10.2
+ numpy: 1.19.2
+ pandas: 1.1.5
+ tqdm: 4.63.0
