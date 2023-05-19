# 迷你骆驼:一系列蒸馏指令数据得到的中文语言模型

[![Code License](https://img.shields.io/badge/Code%20License-Apache_2.0-green.svg)]()
[![Data License](https://img.shields.io/badge/Data%20License-CC%20By%20NC%204.0-red.svg)]()

<p align="center"> <a href="https://scholar.google.com/citations?user=imroB-8AAAAJ&hl=zh-CN" target="_blank">黄钟健 @ 西安电子科大</a>, <a href="https://github.com/LC1332" target="_blank">李鲁鲁 @ 商汤科技</a></p>


<details>
  <summary> 黄钟健 训练了本项目的第一个模型 </summary>

李鲁鲁发起了项目，并提出了后续使用feature进行蒸馏的思路。

黄钟健 训练了本项目的第一个模型，并且实现了训练框架

后续如果更多其他的同学训练小模型，我们也会陆续加入到作者列表中

</details>

受到[LaMini-LM](https://github.com/mbzuai-nlp/LaMini-LM)项目的启发，迷你骆驼是一组小型高效的语言模型，是从ChatGPT蒸馏而来，并使用1500万条指令的大规模数据集进行训练。我们将应用不同模型架构、大小进行训练。并争取在后续评估他们的效果。目前我们已经释放了3.5B的模型。

骆驼嵌入是[Luotuo(骆驼)](https://github.com/LC1332/Luotuo-Chinese-LLM)的子项目之一, 后者由李鲁鲁, 冷子昂, 陈启源发起。


---

- [快速上手](#快速上手)
- [数据](#数据)
- [模型](#模型)
- [Citation](#citation)

---


## 快速上手



## 数据

我们使用Luotuo项目中的翻译数据以及其他项目提供的数据。具体训练文件名以及所含指令数量如下包含：

|Dataset Name| Instruction Number|
|--| -- |
| luotuo_all_data.json              |         168886 |
| alpaca_gpt4_data_zh.json          |         48818 | 
| coig_data.json                    |         165531 |
| baike_all_data_rs150000.json      |         150000 |
| web_text_all_data_rs150000.json   |         150000 |

- Luotuo_all是骆驼项目收集的部分翻译数据。
- alpaca_gpt4_data_zh 从这里进行[下载](https://huggingface.co/datasets/shibing624/alpaca-zh)

后三个数据集参考的[PandasLLM](https://github.com/dandelionsllm/pandallm)的数据集，并进行了重新整理与采样。
- [Chinese Open Instruction Generalist (COIG)](https://huggingface.co/datasets/BAAI/COIG)
- [百科问答(baike2018qa)，150万个带问题类型的问答](https://github.com/brightmart/nlp_chinese_corpus)
- [社区问答json版(webtext2019zh)社区问答json版(webtext2019zh)](https://github.com/brightmart/nlp_chinese_corpus)

## 模型

你可以在下面的表格中，找到迷你骆驼系列模型的下载链接。

<table>
<thead>
  <tr>
    <th>基模型(预训练)</th>
    <th colspan="4">迷你骆驼系列(#parameters)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>GPT2(Wenzhong) </td>
    <td><a href="https://github.com/LC1332/Mini-Luotuom" target="_blank" rel="noopener noreferrer"> 110M(coming soon)</a></td>
    <td><a href="https://huggingface.co/Midkey/GPT2-3.5B-chinese-ft-luotuo" target="_blank" rel="noopener noreferrer">Mini-Luotuo-3.5B</a></td>
    <td></td>
  </tr>
  <tr>
    <td>GPT2(zero_nlp) </td>
    <td><a href="https://github.com/LC1332/Mini-Luotuom" target="_blank" rel="noopener noreferrer"> 312M(coming soon)</a></td>
  </tr>
   <!-- <tr>
        <td>Flan-T5</td>
        <td><a href="https://huggingface.co/MBZUAI/lamini-flan-t5-77m" target="_blank" rel="noopener noreferrer">LaMini-Flan-T5-77M</a>✩</td>
        <td><a href="https://huggingface.co/MBZUAI/lamini-flan-t5-248m" target="_blank" rel="noopener noreferrer">LaMini-Flan-T5-248M</a>✩</td>
        <td><a href="https://huggingface.co/MBZUAI/lamini-flan-t5-783m" target="_blank" rel="noopener noreferrer">LaMini-Flan-T5-783M</a>✩</td>
    <td></td> -->
  <!-- </tr>
    <tr>
    <td>Cerebras-GPT</td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-cerebras-111m" target="_blank" rel="noopener noreferrer">LaMini-Cerebras-111M</a></td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-cerebras-256m" target="_blank" rel="noopener noreferrer">LaMini-Cerebras-256M</a></td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-cerebras-590m" target="_blank" rel="noopener noreferrer">LaMini-Cerebras-590M</a></td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-cerebras-1.3b" target="_blank" rel="noopener noreferrer">LaMini-Cerebras-1.3B</a></td>
  </tr> -->
  <!-- <tr>
    <td>GPT-2</td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-gpt-124m" target="_blank" rel="noopener noreferrer">LaMini-GPT-124M</a>✩</td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-gpt-774m" target="_blank" rel="noopener noreferrer">LaMini-GPT-774M</a>✩</td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-gpt-1.5b" target="_blank" rel="noopener noreferrer">LaMini-GPT-1.5B</a>✩</td>
    <td></td>
  </tr> -->
  <!-- <tr>
    <td>GPT-Neo</td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-neo-125m" target="_blank" rel="noopener noreferrer">LaMini-Neo-125M</a></td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-neo-1.3b" target="_blank" rel="noopener noreferrer">LaMini-Neo-1.3B</a></td>
    <td></td>
    <td></td>
  </tr> -->
  <!-- <tr>
    <td>GPT-J</td>
    <td colspan="4">coming soon</td>
  </tr>
  <tr>
    <td>LLaMA</td>
    <td colspan="4">coming soon</td>
  </tr> -->
</tbody>
</table>




<p align="center" width="100%"><a href="https://github.com/mbzuai-nlp/LaMini-LM/" target="github">GitHub</a>, <a href="https://arxiv.org/abs/2304.14402" target="github">Paper</a></p>

<p align="center" width="100%">
    <a><img src="images/lamini-pipeline.drawio.png" alt="Title" style="width: 90%; min-width: 300px; display: block; margin: auto;"></a>
</p>


## Data

We distill the knowledge from large language models by performing sentence/offline distillation (Kim and Rush, 2016). We generate a total of **2.58M** pairs of instructions and responses using [`gpt-3.5-turbo`](https://openai.com/api/) based on several existing resources of prompts, including [self-instruct](https://github.com/yizhongw/self-instruct) (Wang et al., 2022), [P3](https://huggingface.co/datasets/bigscience/P3) (Sanh et al., 2022), [Flan](https://github.com/google-research/FLAN) (Longpre et al., 2023) and [Alpaca](https://github.com/tatsu-lab/stanford_alpaca) (Taori et al., 2023). More information about the process for generating our instruction dataset, please refer to [our paper](https://arxiv.org/abs/2304.14402).

We release our data [HERE](https://huggingface.co/datasets/MBZUAI/LaMini-instruction). 

Each sample contain the following two fields:
* `instruction`: `string`, describes the task that the model is expected to perform.
* `response`: `string`, the response to the instruction as generated by `gpt-3.5-turbo`.
* `instruction_source`: `string`, the source of a instruction. The possible values are `{'alpaca', 'generated_flan', 'generated_p3', 'original_flan', 'original_p3', 'self_instruct_with_topic', 'self_instruct_without_topic'}`. 

Two examples in our LaMini-instruction data:
```json
{
    "instruction": "What is the capital of Australia?\n\nIs Canberra the only city chosen to serve as a capital due to a compromise between Sydney and Melbourne?", 
    "response": "The capital of Australia is Canberra. Yes, Canberra was chosen as the capital of Australia in 1908 due to a compromise between Sydney and Melbourne, as neither city wanted the other to become the capital.",
    "instruction_source": "generated_flan"
}
```

```json
{
    "instruction": "Create a poem that has the word \"ocean\" in every other line.", 
    "response": "The ocean's depth is a mystery,\nIts waves crashing with energy.\nSalt air fills the coastal scene,\nThe ocean's blue hues pure and clean.\n\nSeagulls cry out a melancholy song,\nThe ocean's rhythm steady and strong.\nSunsets paint the water gold,\nThe ocean's secrets forever untold.",
    "instruction_source": "self_instruct_without_topic"
}
```

## Models

You can download LaMini-LM series as follows. Models with ✩ are those with the best overall performance given their size/architecture, hence we recommend using them. More details can be seen in [our paper](https://arxiv.org/abs/2304.14402). 

<table>
<thead>
  <tr>
    <th>Base model</th>
    <th colspan="4">LaMini-LM series (#parameters)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>T5</td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-t5-61m" target="_blank" rel="noopener noreferrer">LaMini-T5-61M</a></td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-t5-223m" target="_blank" rel="noopener noreferrer">LaMini-T5-223M</a></td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-t5-738m" target="_blank" rel="noopener noreferrer">LaMini-T5-738M</a></td>
    <td></td>
  </tr>
   <tr>
        <td>Flan-T5</td>
        <td><a href="https://huggingface.co/MBZUAI/lamini-flan-t5-77m" target="_blank" rel="noopener noreferrer">LaMini-Flan-T5-77M</a>✩</td>
        <td><a href="https://huggingface.co/MBZUAI/lamini-flan-t5-248m" target="_blank" rel="noopener noreferrer">LaMini-Flan-T5-248M</a>✩</td>
        <td><a href="https://huggingface.co/MBZUAI/lamini-flan-t5-783m" target="_blank" rel="noopener noreferrer">LaMini-Flan-T5-783M</a>✩</td>
    <td></td>
  </tr>
    <tr>
    <td>Cerebras-GPT</td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-cerebras-111m" target="_blank" rel="noopener noreferrer">LaMini-Cerebras-111M</a></td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-cerebras-256m" target="_blank" rel="noopener noreferrer">LaMini-Cerebras-256M</a></td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-cerebras-590m" target="_blank" rel="noopener noreferrer">LaMini-Cerebras-590M</a></td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-cerebras-1.3b" target="_blank" rel="noopener noreferrer">LaMini-Cerebras-1.3B</a></td>
  </tr>
  <tr>
    <td>GPT-2</td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-gpt-124m" target="_blank" rel="noopener noreferrer">LaMini-GPT-124M</a>✩</td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-gpt-774m" target="_blank" rel="noopener noreferrer">LaMini-GPT-774M</a>✩</td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-gpt-1.5b" target="_blank" rel="noopener noreferrer">LaMini-GPT-1.5B</a>✩</td>
    <td></td>
  </tr>
  <tr>
    <td>GPT-Neo</td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-neo-125m" target="_blank" rel="noopener noreferrer">LaMini-Neo-125M</a></td>
    <td><a href="https://huggingface.co/MBZUAI/lamini-neo-1.3b" target="_blank" rel="noopener noreferrer">LaMini-Neo-1.3B</a></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>GPT-J</td>
    <td colspan="4">coming soon</td>
  </tr>
  <tr>
    <td>LLaMA</td>
    <td colspan="4">coming soon</td>
  </tr>

  
</tbody>
</table>

## Using Models
LaMini-LM series and instruction dataset are intended for research use only. (CC BY NC 4.0)

We recommend to use model to reponse to human instructions wrote in natural language. 

We now show you how to load and use our model using HuggingFace `pipeline()`. 
### Encoder-Decoder Models 
```python
# pip install -q transformers
from transformers import pipeline

checkpoint = "{model_name}"

model = pipeline('text2text-generation', model = checkpoint)

input_prompt = 'Please let me know your thoughts on the given place and why you think it deserves to be visited: \n"Barcelona, Spain"'
generated_text = model(input_prompt, max_length=512, do_sample=True)[0]['generated_text']

print("Response", generated_text)
```

### Decoder-Only Models 
For decoder-only models, we used a instruction wrapper to train the model. Hence, we should use the wrapper at inference time. 
```python
# pip install -q transformers
from transformers import pipeline

checkpoint = "{model_name}" 

model = pipeline('text-generation', model = checkpoint)

instruction = 'Please let me know your thoughts on the given place and why you think it deserves to be visited: \n"Barcelona, Spain"'

input_prompt = f"Below is an instruction that describes a task. Write a response that appropriately completes the request.\n\n### Instruction:\n{instruction}\n\n### Response:"

generated_text = model(input_prompt, max_length=512, do_sample=True)[0]['generated_text']

print("Response", generated_text)
```

## Evaluation

### NLP Evaluation 
We use language model evaluation harness ([lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness)) to evaluate our instruction-tuned models. We select 15 diverse NLP tasks, including multiple-choice QA, sentence completion, and sentiment analysis, etc.

<details>
<summary> Details about evaluation datasets (Click to expand) </summary>
<table>
  <caption>NLP evaluation datasets.</caption>
  <thead>
    <tr>
      <th>Clusters</th>
      <th>Dataset</th>
      <th>Size</th>
      <th>Metric</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="5">Multiple-Choice QA</td>
      <td>OpenBookQA</td>
      <td>500</td>
      <td>acc<sub>norm</sub></td>
    </tr>
    <tr>
      <td>SciQ</td>
      <td>1,000</td>
      <td>acc<sub>norm</sub></td>
    </tr>
    <tr>
      <td>RACE</td>
      <td>1,045</td>
      <td>acc</td>
    </tr>
    <tr>
      <td>ARC-C</td>
      <td>1,172</td>
      <td>acc<sub>norm</sub></td>
    </tr>
    <tr>
      <td>PIQA</td>
      <td>1,838</td>
      <td>acc<sub>norm</sub></td>
    </tr>
    <tr>
      <td>Extractive QA</td>
      <td>ReCoRD</td>
      <td>10,000</td>
      <td>F1</td>
    </tr>
    <tr>
      <td>Sentiment Analysis</td>
      <td>SST</td>
      <td>872</td>
      <td>acc</td>
    </tr>
    <tr>
      <td>Paraphrase Identification</td>
      <td>MRPC</td>
      <td>408</td>
      <td>acc</td>
    </tr>
    <tr>
      <td rowspan="3">NLI</td>
      <td>RTE</td>
      <td>277</td>
      <td>acc</td>
    </tr>
    <tr>
      <td>MNLI</td>
      <td>9,815</td>
      <td>acc</td>
    </tr>
    <tr>
      <td>MNLI (mis)</td>
      <td>9,832</td>
      <td>acc</td>
    </tr>
    <tr>
      <td rowspan="2">Coreference Resolution</td>
      <td>WSC</td>
      <td>273</td>
      <td>acc</td>
    </tr>
    <tr>
      <td>WinoGrande</td>
      <td>1,267</td>
      <td>acc</td>
    </tr>
    <tr>
      <td>Word Sense Disambiguation</td>
      <td>WiC</td>
      <td>638</td>
      <td>acc</td>
    </tr>
    <tr>
      <td>Sentence Completion</td>
      <td>HellaSwag</td>
      <td>10,042</td>
      <td>acc<sub>norm</sub></td>
    </tr>
  </tbody>
</table>
</details>
    
The performance comparison between encoder-decoder models and decoder-only models of LaMini-LM family on the downstream NLP tasks. The horizontal dash lines indicate the average performance given by Alpaca-7B and LLaMa-7B.
<p align="center" width="100%">
    <a><img src="images/model_archs.png" alt="nlp_eval" style="width: 50%; min-width: 300px; display: block; margin: auto;"></a>
</p>

> **Warning**
>  __**The reported LLaMA results are not comparable to ours**__, as the LLaMA authors did not provide sufficient details for reproducible evaluation. We use lm-eval-harnesss to measure the performance. [You can replicate the result yourselves](https://github.com/EleutherAI/lm-evaluation-harness). As for our LaMini-LM decoder-only models, we modify lm-eval-harness to [add prompt wrapper for each instruction](https://github.com/afaji/lm-evaluation-harness/blob/master/lm_eval/evaluator.py#L222-L227). You can use our [bash script](https://github.com/afaji/lm-evaluation-harness/blob/master/run_loop.sh) to run the evaluation.

### Human Evaluation

Human evaluation results of the selected models on our 114 user-oriented instructions.
<div class="footnote">
  <ul>
    <li><b>Rate-A</b>: Valid, acceptable and satisfying;</li>
    <li><b>Rate-B</b>: The response is acceptable but has minor errors that can be improved;</li>
    <li><b>Rate-C</b>: The response is relevant and responds to the instruction, but it has significant errors in the content;</li>
    <li><b>Rate-D</b>: Invalid and unacceptable response.</li>
  </ul>
</div>


<p align="center" width="100%">
    <a><img src="images/human_eval_user.png" alt="human_eval" style="width: 80%; min-width: 300px; display: block; margin: auto;"></a>
</p>

### Qualitative Analysis
Model responses to the instruction ``Include important study notes and key points that someone should know about the given subject: "history of the USA"``, where Alpaca-7B fails but LaMini-LMs manage to respond. The high-quality contents are highlighted in blue. The errors are highlighted in red.

<p align="center" width="100%">
    <a><img src="images/generate1.png" alt="generate1" style="width: 80%; min-width: 300px; display: block; margin: auto;"></a>
</p>

Model responses to the instruction ``Write a short description about the given movie or series: "The Witcher (2019)"``, where LaMini-LMs fails but Alpaca-7B manages to respond. The high-quality contents are highlighted in blue. The errors are highlighted in red.
<p align="center" width="100%">
    <a><img src="images/generate2.png" alt="generate2" style="width: 80%; min-width: 300px; display: block; margin: auto;"></a>
</p>

## Citation
Please cite us if you use our data or models.
```bibtex
@article{lamini-lm,
  author       = {Minghao Wu and
                  Abdul Waheed and
                  Chiyu Zhang and
                  Muhammad Abdul-Mageed and
                  Alham Fikri Aji
                  },
  title        = {LaMini-LM: A Diverse Herd of Distilled Models from Large-Scale Instructions},
  journal      = {CoRR},
  volume       = {abs/2304.14402},
  year         = {2023},
  url          = {https://arxiv.org/abs/2304.14402},
  eprinttype   = {arXiv},
  eprint       = {2304.14402}
}
```
