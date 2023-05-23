# 迷你骆驼:一系列蒸馏指令数据得到的中文语言模型

[![Code License](https://img.shields.io/badge/Code%20License-Apache_2.0-green.svg)]()
[![Data License](https://img.shields.io/badge/Data%20License-CC%20By%20NC%204.0-red.svg)]()

<p align="center"> <a href="https://scholar.google.com/citations?user=imroB-8AAAAJ&hl=zh-CN" target="_blank">黄钟健 @ 西安电子科大</a>, <a href="https://github.com/LC1332" target="_blank">李鲁鲁 @ 商汤科技</a></p>

<p align="center">
    <img src="images/ProjectIcon.png" height="300">
</p>


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
- [模型](#模型)
- [数据](#数据)
- [引用](#引用)
- [赞助](#赞助)

---


## 快速上手

初步的Colab代码： <a href="https://colab.research.google.com/github/LC1332/Mini-Luotuo/blob/main/3.5B_minimal.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>

TODO: 实现一个gradio的代码

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
</tbody>
</table>


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

我们将会研究数据协议，如果这些子项目的协议允许的话，我们会陆续发布完整或者抽样后的训练集。

## 训练代码

训练代码使用的[Llama-x](https://github.com/AetherCortex/Llama-X), 并进行相应的修改。

<a name="sponsorship"></a>

## 赞助(Sponsorship) 骆驼项目

如果你有兴趣赞助骆驼项目，请点击[主项目](https://github.com/LC1332/Luotuo-Chinese-LLM#%E8%B5%9E%E5%8A%A9sponsorships)或者查看[赞助表单](https://github.com/LC1332/Luotuo-Chinese-LLM/blob/main/data/Sponsorship_and_balance.md)

If you are interested in sponsoring the [Luotuo Project](https://github.com/LC1332/Luotuo-Chinese-LLM#%E8%B5%9E%E5%8A%A9sponsorships), please click on the [major project](https://github.com/LC1332/Luotuo-Chinese-LLM) or view the [sponsorship form](https://github.com/LC1332/Luotuo-Chinese-LLM/blob/main/data/Sponsorship_and_balance.md).

[回到开头](#BigTitle)


## 引用

如果您在项目中使用了我们的模型、代码或者数据，请引用这个repo。

Please cite the repo if you use the data or code in this repo.

```
@misc{alpaca,
  author={Jianzhong Huang, Cheng Li},
  title = {Mini-Luotuo: A Diverse Herd of Distilled Chinese Models from Large-Scale Instructions},
  year = {2023},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/LC1332/Mini-Luotuo}},
}
```

原来项目的repo

```
@misc{alpaca,
  author={Ziang Leng, Qiyuan Chen and Cheng Li},
  title = {Luotuo: An Instruction-following Chinese Language model, LoRA tuning on LLaMA},
  year = {2023},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/LC1332/Luotuo-Chinese-LLM}},
}
```