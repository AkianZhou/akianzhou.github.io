---
layout: post
title: Improving Language Understanding by Generative Pre-Training
date: 2023-08-03 14:56 +0800
---

<center><big><b>Improving Language Understanding by Generative Pre-Training</b></big></center>
<center><big><b>通过生成预训练提高语言理解能力</b></big></center>

|  Alec Radford   |  Karthik Narasimhan  |  Tim Salimans   | Ilya Sutskever  |
|  ----  | ----  |  ----  | ----  |
| OpenAI  | OpenAI | OpenAI  | OpenAI |
| alec@openai.com  | karthikn@openai.com | tim@openai.com  | ilyasu@openai.com |

<center><b>Abstract</b></center>
<center><b>摘要</b></center>

Natural language understanding comprises a wide range of diverse tasks such as textual entailment, question answering, semantic similarity assessment, and document classification. Although large unlabeled text corpora are abundant, labeled data for learning these specific tasks is scarce, making it challenging for discriminatively trained models to perform adequately. We demonstrate that large gains on these tasks can be realized by generative pre-training of a language model on a diverse corpus of unlabeled text, followed by discriminative fine-tuning on each specific task.In contrast to previous approaches, we make use of task-aware input transformations during fine-tuning to achieve effective transfer while requiring minimal changes to the model architecture. We demonstrate the effectiveness of our approach on a wide range of benchmarks for natural language understanding. Our general task-agnostic model outperforms discriminatively trained models that use architectures specifically crafted for each task, significantly improving upon the state of the art in 9 out of the 12 tasks studied. For instance, we achieve absolute improvements of 8.9% on commonsense reasoning (Stories Cloze Test), 5.7% on question answering (RACE), and 1.5% on textual entailment (MultiNLI).
自然语言理解包含了各种不同的任务，例如文本推理、问答、语义相似度评估和文档分类等。尽管大量未标注的文本语料库非常丰富，但是对于学习这些特定任务的标注数据却很少，这使得训练出具有区分能力的模型能够充分表现面临挑战。我们证明，通过在不同的未标注文本语料库对语言模型进行生成式预训练，然后对每个任务判别性微调，能够在这些任务上获取最大的收益。与之前的方法相比，我们在微调期间通过任务感知输入转换实现有效输入，同时对模型结构进行最小程度更改。我们在自然语言理解的大量基础论证上证明我们方法的有效性。我们的通用任务无关模型优于针对每个任务专门设计的、经过判别式训练的模型，在12项任务中有9项显著超过现有技术水平。例如，我们在常识推理（Stories Cloze Test）取得8.9%的绝对改进，在问题回答（RACE）取得5.7%的绝对改进，在文本蕴含（MultiNLI）取得1.5%的绝对改进。

