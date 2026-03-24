# 案例库

本章收录了来自 Karpathy 讲座的全部案例，作为各章精华案例的完整补充。

---

## FineWeb数据集构建流程

**来源**：Deep Dive into LLMs like ChatGPT  

**对应框架**：第2章：一切都是压缩 / 第8章：三阶段炼金术 / 第13章：参差不齐的前沿


**情境**：Hugging Face 构建 FineWeb 数据集的完整流程：从 Common Crawl（27 亿网页，2007 年起索引）开始，经过 URL 过滤、文本提取、质量过滤、去重，最终获得约 44TB 的高质量多样化训练文本。


**关键时刻**：每个过滤步骤都经过精心设计——仅质量过滤一步就淘汰了大量内容，但保留了内容的多样性。


**结果**：证明了数据工程的价值：原始数据量很大，但真正高质量的训练数据需要大量工程工作来提炼。


**启示**：数据质量和多样性比原始数量更重要。所有主要 LLM 提供商都有类似的内部数据集。


**可迁移场景**：在任何数据密集型项目中，投资于数据清洗和质量保证的时间往往比花在模型架构上的时间产生更大的回报。


---


## Wikipedia斑马条目的逐字复现

**来源**：Deep Dive into LLMs like ChatGPT  

**对应框架**：第2章：一切都是压缩 / 第8章：三阶段炼金术 / 第13章：参差不齐的前沿


**情境**：将维基百科斑马词条的第一句话输入基础语言模型（未经微调的版本）。


**关键时刻**：模型以惊人的准确性逐字复现了整篇文章——包括精确的措辞、数字统计和结构。


**结果**：展示了高频训练数据被模型权重字面记忆的现象。这篇文章在训练数据中被收录了足够多次。


**启示**：模型的"知识"不都是概率性的——对于高度重复的内容，它实际上是记忆存储。这解释了为什么 LLM 在常见问题上非常准确，在罕见问题上会幻觉。


**可迁移场景**：评估 LLM 可靠性时，考虑信息在训练数据中的覆盖频率。常见知识 = 高可信；罕见或专有信息 = 需核实。


---


## 2024选举幻觉案例

**来源**：Deep Dive into LLMs like ChatGPT  

**对应框架**：第2章：一切都是压缩 / 第8章：三阶段炼金术 / 第13章：参差不齐的前沿


**情境**：一个知识截止日期在 2024 年大选之前的模型，被给予提示词"2024 年美国大选中，共和党候选人特朗普……"


**关键时刻**：模型流畅地生成了一套完整的"平行宇宙"——错误的竞选搭档、不存在的辩论、虚构的选举结果，语气自信，毫无犹豫。


**结果**：一个经典的幻觉案例：模型用统计上最合理的续写填充了知识空白。


**启示**：模型的自信程度和准确程度之间没有直接关系。流畅自信的输出可能是完全错误的。


**可迁移场景**：询问 LLM 需要精确事实的问题时（近期事件、具体数字、最新状态），永远独立核实。


---


## DeepSeek R1数学推理涌现

**来源**：Deep Dive into LLMs like ChatGPT  

**对应框架**：第2章：一切都是压缩 / 第8章：三阶段炼金术 / 第13章：参差不齐的前沿


**情境**：DeepSeek 团队用纯 RL（只有数学题正确性作为奖励）训练推理模型。


**关键时刻**：训练数万步后，模型开始在解题中途插入"等等等等，让我重新从头想想"并切换策略——这个行为从未被明确示范，完全自发涌现。


**结果**：模型自主发现了回溯、多角度验证、自我纠错等认知策略，推理能力大幅提升。


**启示**：当你有明确的可评估目标时，RL 可以发现人类从未明确教授的解决策略。优化压力创造了认知创新。


**可迁移场景**：在任何有明确评估标准的技能领域，迭代+反馈循环（类似 RL）往往比学习示范更有效。


---


## Falcon模型身份幻觉

**来源**：Deep Dive into LLMs like ChatGPT  

**对应框架**：第2章：一切都是压缩 / 第8章：三阶段炼金术 / 第13章：参差不齐的前沿


**情境**：Falcon被问及谁创建了它时，声称是OpenAI基于GPT-3构建，因从未被明确告知身份，默认为训练数据中最常见的模式


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## SFT数据创建过程

**来源**：Deep Dive into LLMs like ChatGPT  

**对应框架**：第2章：一切都是压缩 / 第8章：三阶段炼金术 / 第13章：参差不齐的前沿


**情境**：外包人员为多样化提示词撰写理想助手回复，微调基础模型学习助手格式和行为


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 上下文窗口 vs 参数记忆对比

**来源**：Deep Dive into LLMs like ChatGPT  

**对应框架**：第2章：一切都是压缩 / 第8章：三阶段炼金术 / 第13章：参差不齐的前沿


**情境**：直接粘贴章节文本 vs 让模型从记忆回忆，上下文版本产生更高质量输出


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Llama 2 70B两个文件

**来源**：[1hr Talk] Intro to Large Language Models  

**对应框架**：第2章：一切都是压缩 / 第12章：LLM 操作系统


**情境**：完整LLM仅需两个文件：140GB参数文件 + 约500行C代码，在MacBook上无需联网即可运行


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 训练算力估算

**来源**：[1hr Talk] Intro to Large Language Models  

**对应框架**：第2章：一切都是压缩 / 第12章：LLM 操作系统


**情境**：训练Llama 2需约6000块GPU运行12天，耗资约200万美元，将10TB互联网文本压缩至140GB参数


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## LLM操作系统类比

**来源**：[1hr Talk] Intro to Large Language Models  

**对应框架**：第2章：一切都是压缩 / 第12章：LLM 操作系统


**情境**：LLM如新型操作系统：权重=硬盘，上下文窗口=内存，工具=外设，智能体循环=进程


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 提示注入攻击

**来源**：[1hr Talk] Intro to Large Language Models  

**对应框架**：第2章：一切都是压缩 / 第12章：LLM 操作系统


**情境**：能浏览网页的LLM智能体访问包含'忽略所有先前指令'的恶意页面可能被劫持


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 数据投毒/休眠智能体攻击

**来源**：[1hr Talk] Intro to Large Language Models  

**对应框架**：第2章：一切都是压缩 / 第12章：LLM 操作系统


**情境**：对手向训练数据注入触发短语，使模型在未来提示中出现该短语时恶意行动


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## LLM西部荒野1995时刻

**来源**：[1hr Talk] Intro to Large Language Models  

**对应框架**：第2章：一切都是压缩 / 第12章：LLM 操作系统


**情境**：当前LLM生态系统类比于1995年早期Windows：功能强大但边缘粗糙，安全问题尚未解决


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 浏览器比较深度研究

**来源**：How I Use LLMs  

**对应框架**：第3章：上下文窗口 / 第12章：LLM 操作系统 / 第13章：参差不齐的前沿


**情境**：用ChatGPT深度研究对比Brave vs Arc浏览器隐私问题，最终使Karpathy切换到Brave


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## LLM实验室表格失败案例

**来源**：How I Use LLMs  

**对应框架**：第3章：上下文窗口 / 第12章：LLM 操作系统 / 第13章：参差不齐的前沿


**情境**：深度研究生成的表格遗漏了xAI等重要条目，错误包含了其他公司，演示输出需要人工验证


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Evo 2基因组学论文问答

**来源**：How I Use LLMs  

**对应框架**：第3章：上下文窗口 / 第12章：LLM 操作系统 / 第13章：参差不齐的前沿


**情境**：将30MB论文PDF拖入Claude 3.7，直接提问技术细节，演示上下文内文档问答的强大能力


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 《国富论》互动阅读

**来源**：How I Use LLMs  

**对应框架**：第3章：上下文窗口 / 第12章：LLM 操作系统 / 第13章：参差不齐的前沿


**情境**：使用LLM作为协同读者阅读亚当·斯密1776年著作，解释古语和18世纪经济论点的现代背景


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 血检结果解读

**来源**：How I Use LLMs  

**对应框架**：第3章：上下文窗口 / 第12章：LLM 操作系统 / 第13章：参差不齐的前沿


**情境**：上传20页血检面板截图到ChatGPT，获得脂质面板结果、参考范围和标记的解读


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 高级语音视频模式演示

**来源**：How I Use LLMs  

**对应框架**：第3章：上下文窗口 / 第12章：LLM 操作系统 / 第13章：参差不齐的前沿


**情境**：在手机上启用视频的高级语音：指向声学泡沫、书籍、CO2监测器(713ppm)、指环王地图——模型实时正确识别所有物品


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 韩语词汇提取器自定义GPT

**来源**：How I Use LLMs  

**对应框架**：第3章：上下文窗口 / 第12章：LLM 操作系统 / 第13章：参差不齐的前沿


**情境**：少样本提示保存为自定义GPT：给定韩语句子，提取词汇为'韩语;英语'格式直接导入闪卡应用


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 乌鸦群体表情包解读

**来源**：How I Use LLMs  

**对应框架**：第3章：上下文窗口 / 第12章：LLM 操作系统 / 第13章：参差不齐的前沿


**情境**：ChatGPT解释乌鸦群体称为'murder'，所以一只乌鸦靠近另一只乌鸦是在'未遂谋杀'，演示LLM在需要广泛世界知识的文化幽默方面的优势


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 长寿补剂成分分析

**来源**：How I Use LLMs  

**对应框架**：第3章：上下文窗口 / 第12章：LLM 操作系统 / 第13章：参差不齐的前沿


**情境**：上传复杂补剂标签图像，让模型转录所有成分，按安全性/证据质量排名，识别功能性成分vs不必要添加剂


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 莎士比亚字符级语言模型

**来源**：Let's Build GPT: From Scratch, in Code  

**对应框架**：第4章：从零构建 / 第6章：注意力机制 / 第7章：Transformer 解剖


**情境**：使用约1MB莎士比亚戏剧训练字符级语言模型，65个字符词汇，训练前生成随机噪音，训练后生成句法合理的莎士比亚风格文本


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 二元模型基线

**来源**：Let's Build GPT: From Scratch, in Code  

**对应框架**：第4章：从零构建 / 第6章：注意力机制 / 第7章：Transformer 解剖


**情境**：单个嵌入表（词汇量×词汇量）将每个输入标记直接映射到下一个标记的logit，~20行PyTorch代码，生成有字母频率统计但无长程连贯性的文本


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 因果掩码三种等价实现

**来源**：Let's Build GPT: From Scratch, in Code  

**对应框架**：第4章：从零构建 / 第6章：注意力机制 / 第7章：Transformer 解剖


**情境**：并排展示：(1)显式循环平均过去标记，(2)规范化下三角矩阵乘法，(3)tril + masked_fill(-inf) + softmax，第三种用于自注意力


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 自注意力头实现

**来源**：Let's Build GPT: From Scratch, in Code  

**对应框架**：第4章：从零构建 / 第6章：注意力机制 / 第7章：Transformer 解剖


**情境**：单个注意力头：线性投影到Q、K、V，Q·Kᵀ * head_size^(-0.5)，因果掩码，softmax，加权求和V


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## GPT-2架构对比

**来源**：Let's Build GPT: From Scratch, in Code  

**对应框架**：第4章：从零构建 / 第6章：注意力机制 / 第7章：Transformer 解剖


**情境**：教程模型与GPT-2几乎相同，差异仅在规模（GPT-2最大1.5B参数 vs 教程~10M）和训练数据，证明ChatGPT/GPT-4是相同架构的大规模版本


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## names.txt bigram model

**来源**：The spelled-out intro to language modeling (makemore Part 1)  

**对应框架**：第4章：从零构建


**情境**：Training on 32,000 names from a government website. The model learns to predict each character given the previous one. After training, it generates new name-like strings such as 'dontel', 'irot', 'zhendi'.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Emma decomposed into bigrams

**来源**：The spelled-out intro to language modeling (makemore Part 1)  

**对应框架**：第4章：从零构建


**情境**：The word 'emma' produces 5 bigrams: .→e, e→m, m→m, m→a, a→. (where '.' is the special start/end token). Each bigram is one training example.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Count matrix → probability matrix

**来源**：The spelled-out intro to language modeling (makemore Part 1)  

**对应框架**：第4章：从零构建


**情境**：A 27×27 matrix N where N[i,j] counts how often character j follows character i. Dividing each row by its sum gives P[i,j], the probability of j given i. Loss on raw counts is ~2.45, with smoothing ~2.47.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Neural net equivalence demonstration

**来源**：The spelled-out intro to language modeling (makemore Part 1)  

**对应框架**：第4章：从零构建


**情境**：A single linear layer with softmax, trained by NLL, converges to the same loss and generates identical samples as the count-based approach. Both W (after training) and the raw count table encode the same information.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Regularization as smoothing

**来源**：The spelled-out intro to language modeling (makemore Part 1)  

**对应框架**：第4章：从零构建


**情境**：Adding 0.01 * W.pow(2).mean() to the loss penalizes large weights, pushing predictions toward uniform. This is exactly Laplace smoothing: setting W=0 gives a completely uniform distribution.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Building the dataset with context window 3

**来源**：Building makemore Part 2: MLP  

**对应框架**：第4章：从零构建


**情境**：For each word in names.txt, we use a sliding window: [., ., .] → e; [., ., e] → m; [., e, m] → m; etc. Each position becomes one training example with 3 integer inputs and 1 integer label.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Embedding lookup

**来源**：Building makemore Part 2: MLP  

**对应框架**：第4章：从零构建


**情境**：C is a 27×2 matrix. For input [5, 13, 13], we look up rows 5, 13, 13 and concatenate to get a 6-dimensional vector: C[5] ++ C[13] ++ C[13].


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## MLP forward pass

**来源**：Building makemore Part 2: MLP  

**对应框架**：第4章：从零构建


**情境**：emb = C[X] (shape: 32×3×2); emb_cat = emb.view(32,6); h = tanh(emb_cat @ W1 + b1) (32×100); logits = h @ W2 + b2 (32×27); loss = F.cross_entropy(logits, Y).


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Learning rate search

**来源**：Building makemore Part 2: MLP  

**对应框架**：第4章：从零构建


**情境**：Running training for 1000 steps with LR exponentially ranging from 1e-3 to 1, then plotting loss vs. LR. The sweet spot is identified and then used for actual training.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Train/val/test split on names.txt

**来源**：Building makemore Part 2: MLP  

**对应框架**：第4章：从零构建


**情境**：80% training (~25,600 words), 10% validation (~3,200), 10% test (~3,200). Training loss ~2.1, validation loss ~2.17 after tuning. Demonstrates overfitting management.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Saturated tanh at initialization

**来源**：Building makemore Part 3: Activations & Gradients, BatchNorm  

**对应框架**：第5章：梯度是诚实的


**情境**：Without proper initialization (weights drawn from N(0,1) for a 10→200 hidden layer), 20% of tanh activations are immediately in the saturated region (|output| > 0.97). These neurons produce near-zero gradients and barely learn.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Hockey-stick loss curve

**来源**：Building makemore Part 3: Activations & Gradients, BatchNorm  

**对应框架**：第5章：梯度是诚实的


**情境**：If the final layer logits are not near-zero at init, the network starts with artificially high cross-entropy loss (~8-9 nats vs. expected ~3.3) because it is confidently wrong. Fixing initialization by scaling W2 by 0.01 produces a flat, correct starting loss.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Kaiming initialization in practice

**来源**：Building makemore Part 3: Activations & Gradients, BatchNorm  

**对应框架**：第5章：梯度是诚实的


**情境**：For a linear layer projecting from fan_in=30 to fan_out=200 followed by tanh, set W = torch.randn(30,200) * (5/3) / sqrt(30). This keeps the standard deviation of activations ~1 through the layer.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## BatchNorm layer sprinkled into MLP

**来源**：Building makemore Part 3: Activations & Gradients, BatchNorm  

**对应框架**：第5章：梯度是诚实的


**情境**：Inserting a BatchNorm1d between the linear layer and tanh: the pre-activation hpreact is normalized to N(0,1) per batch, then scaled by gamma and shifted by beta. Training loss drops faster and is more stable.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Running mean/variance for inference

**来源**：Building makemore Part 3: Activations & Gradients, BatchNorm  

**对应框架**：第5章：梯度是诚实的


**情境**：During training, BatchNorm maintains an EMA of batch mean and variance. At inference, these frozen estimates are used instead of the batch statistics. Forgetting to switch causes NaN/wrong outputs with batch size 1.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Activation/gradient histograms

**来源**：Building makemore Part 3: Activations & Gradients, BatchNorm  

**对应框架**：第5章：梯度是诚实的


**情境**：Plotting histograms of tanh outputs and their gradients across all layers. Healthy training: all layers have similar spread. Pathological: later layers collapse to zero (vanishing) or explode (gradient explosion).


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Building a 2-input expression

**来源**：The spelled-out intro to neural networks and backpropagation  

**对应框架**：第1章：可微分程序 / 第5章：梯度是诚实的


**情境**：a = Value(-4.0); b = Value(2.0); c = a + b; d = a * b + b**3; c += c + 1; q = c.tanh(); ... This constructs a computational graph of ~10 nodes. Calling q.backward() fills in .grad for a and b correctly.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Visualizing the computation graph

**来源**：The spelled-out intro to neural networks and backpropagation  

**对应框架**：第1章：可微分程序 / 第5章：梯度是诚实的


**情境**：Using graphviz, drawing every Value node with its data and grad, and drawing edges for every operation. Shows exactly how + and * connect to produce the final loss.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Manual backprop through tanh

**来源**：The spelled-out intro to neural networks and backpropagation  

**对应框架**：第1章：可微分程序 / 第5章：梯度是诚实的


**情境**：For node o = tanh(n): o.grad was computed by the outer backward; n.grad += (1 - o.data**2) * o.grad. This local gradient of tanh times the chain gradient gives n's contribution to the loss.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Training a 3-layer MLP on 4 examples

**来源**：The spelled-out intro to neural networks and backpropagation  

**对应框架**：第1章：可微分程序 / 第5章：梯度是诚实的


**情境**：Model: 3 inputs → [4 neurons] → [4 neurons] → 1 output. Training data: 4 (x, y) pairs with targets [-1, 1, -1, 1]. Running 20 steps of gradient descent with lr=0.05 reduces loss from ~6.0 to ~0.04.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## PyTorch comparison

**来源**：The spelled-out intro to neural networks and backpropagation  

**对应框架**：第1章：可微分程序 / 第5章：梯度是诚实的


**情境**：Replicating the exact same 2-input expression in PyTorch with requires_grad=True and calling .backward(). The .grad values exactly match micrograd's, validating the implementation.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## exp and division implementation

**来源**：The spelled-out intro to neural networks and backpropagation  

**对应框架**：第1章：可微分程序 / 第5章：梯度是诚实的


**情境**：Value.exp(): out.data = math.exp(self.data); backward sets self.grad += out.data * out.grad (since d/dx e^x = e^x). Division implemented as a * b**(-1).


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Cross-entropy backward pass (Exercise 1 vs Exercise 2)

**来源**：Building makemore Part 4: Becoming a Backprop Ninja  

**对应框架**：第5章：梯度是诚实的


**情境**：Exercise 1: backprop through every atomic operation in the loss (log, indexing, mean, etc.) — ~10 lines. Exercise 2: analytical formula dlogits = softmax(logits); dlogits[range(N), yb] -= 1; dlogits /= N — 3 lines, same result, much faster.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Gradient force visualization

**来源**：Building makemore Part 4: Becoming a Backprop Ninja  

**对应框架**：第5章：梯度是诚实的


**情境**：Visualizing the 32×27 dlogits matrix as an image: most entries are the softmax probability (small positive, pushing down); the correct class entries have that probability minus 1 (net pull up). Each row sums to zero.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Matrix multiplication backward pass

**来源**：Building makemore Part 4: Becoming a Backprop Ninja  

**对应框架**：第5章：梯度是诚实的


**情境**：For logits = h @ W2 + b2: dh = dlogits @ W2.T; dW2 = h.T @ dlogits; db2 = dlogits.sum(0). Derived from a small concrete 2×2 example worked out on paper, then generalized.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Batch norm backward (Exercise 3)

**来源**：Building makemore Part 4: Becoming a Backprop Ninja  

**对应框架**：第5章：梯度是诚实的


**情境**：Single closed-form expression for dhprebn given dhpreact: dhprebn = (1/(N*std)) * (N*dhpreact - dhpreact.sum(0) - xhat*(dhpreact*xhat).sum(0)). Derived by chaining through x_hat, sigma^2, mu, and x on paper.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Embedding gradient via scatter

**来源**：Building makemore Part 4: Becoming a Backprop Ninja  

**对应框架**：第5章：梯度是诚实的


**情境**：dC = torch.zeros_like(C); for k in range(Xb.shape[0]): for j in range(Xb.shape[1]): ix = Xb[k,j]; dC[ix] += dEmb[k,j]. The += handles the case where the same embedding row was used multiple times in a batch.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Full manual backward pass — Exercise 4

**来源**：Building makemore Part 4: Becoming a Backprop Ninja  

**对应框架**：第5章：梯度是诚实的


**情境**：Combining all manually derived gradients, running 200K steps without loss.backward(), and achieving the same final loss and generated names as PyTorch's autograd. The manual backward pass is ~20 lines of code.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## WaveNet tree structure for 8 characters

**来源**：Building makemore Part 5: Building a WaveNet  

**对应框架**：第4章：从零构建


**情境**：Level 0: 8 input chars → 4 pairs, each pair merged into one representation. Level 1: 4 merged pairs → 2 pairs of pairs. Level 2: 2 → 1 final representation → predict next char. Contrast with flat: all 8 → 1 hidden layer immediately.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## FlattenConsecutive module

**来源**：Building makemore Part 5: Building a WaveNet  

**对应框架**：第4章：从零构建


**情境**：Input shape (B=32, T=8, C=24). After FlattenConsecutive(2): shape becomes (32, 4, 48). After second FlattenConsecutive(2): (32, 2, 96). After third: (32, 1, 192). This implements the hierarchical merge.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## BatchNorm eval mode bug

**来源**：Building makemore Part 5: Building a WaveNet  

**对应框架**：第4章：从零构建


**情境**：During sampling, the context is a single example (batch size 1). If BatchNorm is in training mode, it tries to compute variance over 1 example → NaN/garbage. Fix: always call model.eval() before generating samples.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Architecture comparison: flat MLP vs hierarchical

**来源**：Building makemore Part 5: Building a WaveNet  

**对应框架**：第4章：从零构建


**情境**：Flat: C(3) → Linear(6→100) → Tanh → Linear(100→27). Hierarchical WaveNet: C(8) → [(Linear(16→128), Tanh) × 3 levels with FlattenConsecutive] → Linear(128→27). WaveNet achieves ~2.02 val loss vs ~2.17 for flat MLP.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Character-level tokenization baseline

**来源**：Let's build the GPT Tokenizer  

**对应框架**：第9章：分词的蝴蝶效应


**情境**：Shakespeare dataset: 65 unique characters → 65-token vocabulary. Encoding 1,000 characters gives 1,000 tokens. Simple but creates very long sequences for Transformers (quadratic attention cost).


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## BPE from scratch

**来源**：Let's build the GPT Tokenizer  

**对应框架**：第9章：分词的蝴蝶效应


**情境**：Starting with UTF-8 bytes of a small text (e.g., Karpathy's blog post). Initial sequence length: ~616 tokens (bytes). After 20 BPE merges: the most common pair (e.g., [101, 32] = 'e ') is merged into token 256, then [116, 104] into 257, etc. Sequence shrinks with each merge.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## get_stats() and merge() functions

**来源**：Let's build the GPT Tokenizer  

**对应框架**：第9章：分词的蝴蝶效应


**情境**：get_stats([5,6,6,7,9,1]) returns {(5,6):1, (6,6):1, (6,7):1, (7,9):1, (9,1):1}. merge([5,6,6,7,9,1], (6,7), 99) returns [5,6,99,9,1]. These two primitives implement the entire BPE training loop.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## tiktoken GPT-2 encoding

**来源**：Let's build the GPT Tokenizer  

**对应框架**：第9章：分词的蝴蝶效应


**情境**：import tiktoken; enc = tiktoken.get_encoding('gpt2'); enc.encode('hello world') → [31373, 995]. The 50,257-token vocabulary handles any text via BPE on UTF-8 bytes.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Special token <|endoftext|>

**来源**：Let's build the GPT Tokenizer  

**对应框架**：第9章：分词的蝴蝶效应


**情境**：Token ID 50256 in GPT-2. Used to delimit separate documents in training data so the model learns that nothing from one document should predict anything in the next. Must be handled specially (not produced by regular BPE merges).


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## LLM arithmetic failures traced to tokenization

**来源**：Let's build the GPT Tokenizer  

**对应框架**：第9章：分词的蝴蝶效应


**情境**：The string '127 + 677 = 804' may tokenize inconsistently: '127' might be one token but '677' might split into '6','77'. The model never sees the raw digits — it sees arbitrary token IDs — making arithmetic difficult.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## FIM (Fill In the Middle) special tokens

**来源**：Let's build the GPT Tokenizer  

**对应框架**：第9章：分词的蝴蝶效应


**情境**：GPT-4's tokenizer adds 4 special tokens: <|fim_prefix|>, <|fim_middle|>, <|fim_suffix|>, <|fim_pad|>. These enable the model to predict missing text between a prefix and suffix, a technique from a 2022 paper.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## GPT-2 architecture from scratch

**来源**：Let's reproduce GPT-2 (124M)  

**对应框架**：第10章：规模定律与现代训练实践


**情境**：Implementing GPT-2 config (n_layer=12, n_head=12, n_embd=768, vocab_size=50257, block_size=1024), CausalSelfAttention, MLP (GELU activation, 4x expansion), Block (pre-LN), and GPT class. Loading pretrained weights from HuggingFace and verifying they match.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Weight initialization matching GPT-2

**来源**：Let's reproduce GPT-2 (124M)  

**对应框架**：第10章：规模定律与现代训练实践


**情境**：nn.Linear initialized with std=0.02; nn.Embedding with std=0.02; residual projection layers additionally scaled by 1/sqrt(2*n_layers) ≈ 0.03 for 12 layers. This matches OpenAI's original initialization.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Flash attention speedup

**来源**：Let's reproduce GPT-2 (124M)  

**对应框架**：第10章：规模定律与现代训练实践


**情境**：Replacing manual QKV attention (softmax of QK^T/sqrt(d) masked with attention mask, then @V) with F.scaled_dot_product_attention() achieves ~7-8x speedup due to kernel fusion that avoids materializing the N×N matrix.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Gradient accumulation for large batch

**来源**：Let's reproduce GPT-2 (124M)  

**对应框架**：第10章：规模定律与现代训练实践


**情境**：Target: B=0.5M tokens (as in GPT-3 paper). With micro_batch=16 and seq_len=1024, each step processes 16K tokens. Grad accumulation steps = 500K/16K ≈ 32. Gradients are accumulated over 32 forward passes, then one optimizer step.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## AdamW optimizer configuration

**来源**：Let's reproduce GPT-2 (124M)  

**对应框架**：第10章：规模定律与现代训练实践


**情境**：Weight decay 0.1 applied to 2D+ parameters (weight matrices) but NOT to biases, embeddings, or LayerNorm parameters. Parameter groups separated: decay_params vs. no_decay_params. Using fused=True for speed.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Cosine LR schedule with warmup

**来源**：Let's reproduce GPT-2 (124M)  

**对应框架**：第10章：规模定律与现代训练实践


**情境**：Linear warmup from 0 to max_lr over 715 steps (375M tokens / 0.5M per step). Then cosine decay from max_lr=6e-4 to min_lr=6e-5 over remaining steps. Implemented as a custom get_lr() function called before each optimizer step.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## Hellaswag evaluation

**来源**：Let's reproduce GPT-2 (124M)  

**对应框架**：第10章：规模定律与现代训练实践


**情境**：Each Hellaswag example: a context with 4 possible completions. For each completion, compute average token NLL under the model; choose lowest-loss completion. Plotting accuracy over training steps to track progress against published GPT-2 results.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## DDP multi-GPU training

**来源**：Let's reproduce GPT-2 (124M)  

**对应框架**：第10章：规模定律与现代训练实践


**情境**：Using torch.distributed + nccl backend. Each process handles 1 GPU; DDP wrapper syncs gradients via allreduce only on the last accumulation step (model.require_backward_grad_sync = False during accumulation). 8 GPUs → 1.5M tokens/second throughput.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## torch.compile effect

**来源**：Let's reproduce GPT-2 (124M)  

**对应框架**：第10章：规模定律与现代训练实践


**情境**：Adding torch.compile(model) after model creation compiles the full computation graph, fusing operations and reducing Python interpreter calls. Training step time drops from ~250ms to ~130ms on A100.


**启示**：本案例展示了 Karpathy 讲座中的核心概念，与对应章节的框架直接相关。


---


## 覆盖统计


共收录 75 / 75 个案例（覆盖率 100%）
