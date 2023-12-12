# Awesome-Language-Model-on-Graphs [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of papers and resources about large language models (LLMs) on graphs based on our survey paper: [Large Language Models on Graphs: A Comprehensive Survey](https://arxiv.org/abs/2312.02783). 

<p align="center">
    <img src="./intro.svg" width="90%" style="align:center;"/>
</p>

## Why LLMs on graphs?

Large language models (LLMs), such as ChatGPT and LLaMA, are creating significant advancements in natural language processing, due to their strong text encoding/decoding ability and newly found emergent capability (e.g., reasoning).
While LLMs are mainly designed to process pure texts, there are many real-world scenarios where text data are associated with rich structure information in the form of graphs (e.g., academic networks, and e-commerce networks) or scenarios where graph data are captioned with rich textual information (e.g., molecules with descriptions).
Besides, although LLMs have shown their pure text-based reasoning ability, it is underexplored whether such ability can be generalized to graph scenarios (i.e., graph-based reasoning).
In this paper, we provide a comprehensive review of scenarios and techniques related to large language models on graphs.

## Contents

- [Awesome-Language-Model-on-Graphs ](#awesome-language-model-on-graphs-)
  - [Why LLMs on graphs?](#why-llms-on-graphs)
  - [Contents](#contents)
    - [Keywords Convention](#keywords-convention)
  - [Perspectives](#perspectives)
  - [Pure Graphs](#pure-graphs)
    - [Datasets](#datasets)
    - [Direct Answering](#-direct-answering)
    - [Heuristic Reasoning](#-heuristic-reasoning)
    - [Algorithmic Reasoning](#-algorithmic-reasoning)
  - [Text-Rich Graphs](#text-rich-graphs)
    - [Datasets](#datasets-1)
    - [LLM as Predictor (Node)](#-llm-as-predictor-node)
      - [Graph As Sequence (Node)](#graph-as-sequence-node)
      - [Graph-Empowered LLM (Node)](#graph-empowered-llm-node)
      - [Graph-Aware LLM Finetuning](#graph-aware-llm-finetuning)
    - [LLM as Encoder](#-llm-as-encoder)
      - [Optimization](#optimization)
      - [Data Augmentation](#data-augmentation)
      - [Knowledge Distillation](#knowledge-distillation)
    - [LLM as Aligner (Node)](#-llm-as-aligner-node)
      - [Prediction Alignment](#prediction-alignment)
      - [Latent Space Alignment (Node)](#latent-space-alignment-node)
  - [Text-Paired Graphs (Molecules)](#text-paired-graphs-molecules)
    - [Datasets](#datasets-2)
    - [LLM as Predictor (Graph)](#-llm-as-predictor-graph)
      - [Graph As Sequence](#graph-as-sequence)
      - [Graph-Empowered LLM (Graph)](#graph-empowered-llm-graph)
    - [LLM as Aligner (Graph)](#-llm-as-aligner-graph)
      - [Latent Space Alignment (Graph)](#latent-space-alignment-graph)
  - [Contribution](#contribution)
  - [Citations](#citations)


### Keywords Convention

![](https://img.shields.io/badge/EncoderOnly-blue) The Transformer architecture used in the work, e.g., EncoderOnly, DecoderOnly, EncoderDecoder.

![](https://img.shields.io/badge/Medium-red) The size of the large language model, e.g., medium (i.e., less than 1B parameters), LLM (i.e., more than 1B parameters).


## Perspectives
1. **Unifying Large Language Models and Knowledge Graphs: A Roadmap.** `preprint`

    *Shirui Pan, Linhao Luo, Yufei Wang, Chen Chen, Jiapu Wang, Xindong Wu* [[PDF](https://arxiv.org/pdf/2306.08302.pdf)], 2023.6

1. **Integrating Graphs with Large Language Models: Methods and Prospects** `preprint`
    
    *Shirui Pan, Yizhen Zheng, Yixin Liu* [[PDF](https://arxiv.org/pdf/2310.05499.pdf)], 2023.10

1. **Towards graph foundation models: A survey and beyond.** `preprint`

    *Jiawei Liu, Cheng Yang, Zhiyuan Lu, Junze Chen, Yibo Li, Mengmei Zhang, Ting Bai, Yuan Fang, Lichao Sun, Philip S. Yu, Chuan Shi.* [[PDF](https://arxiv.org/pdf/2310.11829.pdf)], 2023.10

1. **A Survey of Graph Meets Large Language Model: Progress and Future Directions.** `preprint`

    *Yuhan Li, Zhixun Li, Peisong Wang, Jia Li, Xiangguo Sun, Hong Cheng, Jeffrey Xu Yu.* [[PDF](https://arxiv.org/pdf/2311.12399.pdf)], 2023.11


## Pure Graphs

### <img src="./star.svg" width="15" height="15" /> Datasets
Table 3 in our survey paper [Large Language Models on Graphs: A Comprehensive Survey](https://arxiv.org/abs/2312.02783).
<p align="center">
    <img src="./puregraph-data.jpg" width="90%" style="align:center;"/>
</p>


### <img src="./star.svg" width="15" height="15" /> Direct Answering
1. **Can Language Models Solve Graph Problems in Natural Language?** `preprint`

    *Heng Wang, Shangbin Feng, Tianxing He, Zhaoxuan Tan, Xiaochuang Han, Yulia Tsvetkov.* [[PDF](https://browse.arxiv.org/pdf/2305.10037.pdf)] [[Code](https://github.com/Arthur-Heng/NLGraph)], 2023.5, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

2. **GPT4Graph: Can Large Language Models Understand Graph Structured Data ? An Empirical Evaluation and Benchmarking.** `preprint`

    *Jiayan Guo, Lun Du, Hengyu Liu, Mengyu Zhou, Xinyi He, Shi Han.* [[PDF](https://arxiv.org/abs/2305.15066)], 2023.5, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

3. **Evaluating Large Language Models on Graphs: Performance Insights and Comparative Analysis.** `preprint`

    *Chang Liu, Bo Wu.* [[PDF](https://arxiv.org/abs/2308.11224)] [[Code](https://github.com/Ayame1006/LLMtoGraph)], 2023.8, [[PDF](https://arxiv.org/abs/2305.15066)], 2023.5, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

4. **Talk Like A Graph: Encoding Graphs For Large Language Models.** `preprint`

    *Bahare Fatemi, Jonathan Halcrow, Bryan Perozzi.* [[PDF](https://arxiv.org/pdf/2310.04560.pdf)], 2023.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

5. **GraphLLM: Boosting Graph Reasoning Ability of Large Language Model.** `preprint`

    *Ziwei Chai, Tianjie Zhang, Liang Wu, Kaiqiao Han, Xiaohai Hu, Xuanwen Huang, Yang Yang.* [[PDF](https://arxiv.org/pdf/2310.05845.pdf)] [[Code](https://github.com/mistyreed63849/graph-llm)], 2023.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

6. **LLM4DyG: Can Large Language Models Solve Problems on Dynamic Graphs?.** `preprint`

    *Zeyang Zhang, Xin Wang, Ziwei Zhang, Haoyang Li, Yijian Qin, Simin Wu, Wenwu Zhu* [[PDF](https://arxiv.org/pdf/2310.17110.pdf)] [[Code]()], 2023.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

7. **Which Modality should I use - Text, Motif, or Image? : Understanding Graphs with Large Language Models.** `preprint`

    *Debarati Das, Ishaan Gupta, Jaideep Srivastava, Dongyeop Kang* [[PDF](https://arxiv.org/pdf/2311.09862.pdf)] [[Code]()], 2023.11, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

### <img src="./star.svg" width="15" height="15" /> Heuristic Reasoning
1. **StructGPT: A General Framework for Large Language Model to Reason over Structured Data.** `preprint`

    *Jinhao Jiang, Kun Zhou, Zican Dong, Keming Ye, Wayne Xin Zhao, Ji-Rong Wen.* [[PDF](https://arxiv.org/abs/2305.09645)] [[Code](https://github.com/RUCAIBox/StructGPT)], 2023.5, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

2. **Think-on-Graph: Deep and Responsible Reasoning of Large Language Model on Knowledge Graph.** `preprint`

    *Jiashuo Sun, Chengjin Xu, Lumingyuan Tang, Saizhuo Wang, Chen Lin, Yeyun Gong, Lionel M. Ni, Heung-Yeung Shum, Jian Guo.* [[PDF](https://arxiv.org/abs/2307.07697)] [[Code](https://github.com/GasolSun36/ToG)], 2023.7, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

3. **Reasoning on Graphs: Faithful and Interpretable Large Language Model Reasoning.** `preprint`

    *Linhao Luo, Yuan-Fang Li, Gholamreza Haffari, Shirui Pan.* [[PDF](https://arxiv.org/abs/2310.01061)] [[Code](https://github.com/RManLuo/reasoning-on-graphs)], 2023.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)


### <img src="./star.svg" width="15" height="15" /> Algorithmic Reasoning
1. **Graph-ToolFormer: To Empower LLMs with Graph Reasoning Ability via Prompt Augmented by ChatGPT.** `preprint`

    *Jiawei Zhang.* [[PDF](https://arxiv.org/abs/2304.11116)] [[Code](https://github.com/jwzhanggy/Graph_Toolformer)], 2023.4, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)


## Text-Rich Graphs

### <img src="./star.svg" width="15" height="15" /> Datasets
Table 7 in our survey paper [Large Language Models on Graphs: A Comprehensive Survey](https://arxiv.org/abs/2312.02783).
<p align="center">
    <img src="./node-data.jpg" width="90%" style="align:center;"/>
</p>

### <img src="./star.svg" width="15" height="15" /> LLM as Predictor (Node)
#### Graph As Sequence (Node)
1. **MATCH: Metadata-Aware Text Classification in A Large Hierarchy.** `WWW 2021`

    *Yu Zhang, Zhihong Shen, Yuxiao Dong, Kuansan Wang, Jiawei Han.* [[PDF](https://arxiv.org/abs/2102.07349)] [[Code](https://github.com/yuzhimanhua/MATCH)], 2021.2, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

2. **QA-GNN: Reasoning with Language Models and Knowledge Graphs for Question Answering.** `NAACL 2021`

    *Michihiro Yasunaga, Hongyu Ren, Antoine Bosselut, Percy Liang, Jure Leskovec.* [[PDF](https://arxiv.org/abs/2104.06378)] [[Code](https://github.com/michiyasunaga/qagnn)], 2021.4, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

3. **Natural Language is All a Graph Needs.** `preprint`

    *Ruosong Ye, Caiqi Zhang, Runhui Wang, Shuyuan Xu, Yongfeng Zhang.* [[PDF](https://arxiv.org/abs/2308.07134)], 2023.8, ![](https://img.shields.io/badge/DecoderOnly-blue)![](https://img.shields.io/badge/EncoderDecoder-blue) ![](https://img.shields.io/badge/LLM-red)

4. **Can LLMs Effectively Leverage Graph Structural Information: When and Why.** `preprint`

    *Jin Huang, Xingjian Zhang, Qiaozhu Mei, Jiaqi Ma.* [[PDF](https://arxiv.org/abs/2309.16595)] [[Code](https://github.com/TRAIS-Lab/LLM-Structured-Data)], 2023.9, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)
   
5. **Graph Neural Prompting with Large Language Models.** `preprint`

    *Yijun Tian, Huan Song, Zichen Wang, Haozhu Wang, Ziqing Hu, Fang Wang, Nitesh V. Chawla, Panpan Xu.* [[PDF](https://arxiv.org/abs/2309.15427)], 2023.9, ![](https://img.shields.io/badge/DecoderOnly-blue)![](https://img.shields.io/badge/EncoderDecoder-blue) ![](https://img.shields.io/badge/LLM-red)

6. **Prompt-based Node Feature Extractor for Few-shot Learning on Text-Attributed Graphs.** `preprint`

    *Xuanwen Huang, Kaiqiao Han, Dezheng Bao, Quanjin Tao, Zhisheng Zhang, Yang Yang, Qi Zhu.* [[PDF](https://arxiv.org/pdf/2309.02848.pdf)], 2023.9, , ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

7. **GraphText: Graph Reasoning in Text Space.** `preprint`
    
    *Jianan Zhao, Le Zhuo, Yikang Shen, Meng Qu, Kai Liu, Michael Bronstein, Zhaocheng Zhu, Jian Tang* [[PDF](https://arxiv.org/abs/2310.01089)], 2023.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

8. **GraphGPT: Graph Instruction Tuning for Large Language Models.** `preprint`

    *Jiabin Tang, Yuhao Yang, Wei Wei, Lei Shi, Lixin Su, Suqi Cheng, Dawei Yin, Chao Huang.* [[PDF](https://arxiv.org/pdf/2310.13023.pdf)], 2023.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

9. **Learning Multiplex Embeddings on Text-rich Networks with One Text Encoder.** `preprint`

    *Bowen Jin, Wentao Zhang, Yu Zhang, Yu Meng, Han Zhao, Jiawei Han.* [[Paper](https://arxiv.org/abs/2310.06684)][[Code]](https://github.com/PeterGriffinJin/METERN-submit), 2023.10, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

10. **Disentangled Representation Learning with Large Language Models for Text-Attributed Graphs.** `preprint`

    *Yijian Qin, Xin Wang, Ziwei Zhang, Wenwu Zhu.* [[PDF](https://arxiv.org/pdf/2310.18152.pdf)], 2023.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)



#### Graph-Empowered LLM (Node)

1. **Text Generation from Knowledge Graphs with Graph Transformers.** `NAACL 2019`

    *Rik Koncel-Kedziorski, Dhanush Bekal, Yi Luan, Mirella Lapata, Hannaneh Hajishirzi.* [[PDF](https://arxiv.org/abs/1904.02342)] [[Code](https://github.com/rikdz/GraphWriter)], 2019.4, ![](https://img.shields.io/badge/EncoderDecoder-blue) ![](https://img.shields.io/badge/Medium-red)

2. **GraphFormers: GNN-nested Transformers for Representation Learning on Textual Graph.** `NeurIPs 2021`

    *Junhan Yang, Zheng Liu, Shitao Xiao, Chaozhuo Li, Defu Lian, Sanjay Agrawal, Amit Singh, Guangzhong Sun, Xing Xie.* [[Paper](https://arxiv.org/abs/2105.02605)][[Code]](https://github.com/microsoft/GraphFormers), 2021.5, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

3. **GreaseLM: Graph Reasoning Enhanced Language Models for Question Answering.** `ICLR 2022`

    *Xikun Zhang, Antoine Bosselut, Michihiro Yasunaga, Hongyu Ren, Percy Liang, Christopher D Manning and Jure Leskovec.* [[PDF](https://cs.stanford.edu/~myasu/papers/greaselm_iclr22.pdf)] [[Code](https://github.com/snap-stanford/GreaseLM)], 2022.1, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

4. **Heterformer: Transformer-based Deep Node Representation Learning on Heterogeneous Text-Rich Networks.** `KDD 2023`

    *Bowen Jin, Yu Zhang, Qi Zhu, Jiawei Han.* [[Paper](https://arxiv.org/abs/2205.10282)][[Code]](https://github.com/PeterGriffinJin/Heterformer), 2022.5, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

5. **DRAGON: Deep Bidirectional Language-Knowledge Graph Pretraining.** `NeurIPs 2022`

    *Michihiro Yasunaga, Antoine Bosselut, Hongyu Ren, Xikun Zhang, Christopher D. Manning, Percy Liang, Jure Leskovec.* [[Paper](https://cs.stanford.edu/~myasu/papers/dragon_neurips22.pdf)][[Code]](https://github.com/michiyasunaga/dragon), 2022.10, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

6. **Edgeformers: Graph-Empowered Transformers for Representation Learning on Textual-Edge Networks.** `ICLR 2023`

    *Bowen Jin, Yu Zhang, Yu Meng, Jiawei Han.* [[Paper](https://openreview.net/pdf?id=2YQrqe4RNv)][[Code]](https://github.com/PeterGriffinJin/Edgeformers), 2023.1, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

7. **Patton: Language Model Pretraining on Text-rich Networks.** `ACL 2023`

    *Bowen Jin, Wentao Zhang, Yu Zhang, Yu Meng, Xinyang Zhang, Qi Zhu, Jiawei Han.* [[Paper](https://arxiv.org/abs/2305.12268)][[Code]](https://github.com/PeterGriffinJin/Patton), 2023.5, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)



#### Graph-Aware LLM Finetuning

1. **Explaining Relationships Between Scientific Documents.** `ACL 2021`

    *Kelvin Luu, Xinyi Wu, Rik Koncel-Kedziorski, Kyle Lo, Isabel Cachola, Noah A. Smith.* [[PDF](https://arxiv.org/abs/2002.00317)], 2020.2, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

2. **SPECTER: Document-level Representation Learning using Citation-informed Transformers.** `ACL 2020`

    *Arman Cohan, Sergey Feldman, Iz Beltagy, Doug Downey, Daniel S. Weld.* [[Paper](https://arxiv.org/abs/2004.07180)], 2020.4, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

3. **Pre-training for Ad-hoc Retrieval: Hyperlink is Also You Need.** `CIKM 2021`

    *Zhengyi Ma, Zhicheng Dou, Wei Xu, Xinyu Zhang, Hao Jiang, Zhao Cao, Ji-Rong Wen.* [[PDF](https://arxiv.org/abs/2108.09346)] [[Code](https://github.com/zhengyima/anchors)], 2021.8, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)


4. **Neighborhood Contrastive Learning for Scientific Document Representations with Citation Embeddings.** `EMNLP 2022`

    *Junhan Yang, Zheng Liu, Shitao Xiao, Chaozhuo Li, Defu Lian, Sanjay Agrawal, Amit Singh, Guangzhong Sun, Xing Xie.* [[Paper](https://arxiv.org/pdf/2202.06671.pdf)][[Code]](https://github.com/malteos/scincl), 2022.2, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

5. **Metadata-Induced Contrastive Learning for Zero-Shot Multi-Label Text Classification.** `WWW 2022`

    *Yu Zhang, Zhihong Shen, Chieh-Han Wu, Boya Xie, Junheng Hao, Ye-Yi Wang, Kuansan Wang, Jiawei Han.* [[Paper](https://yuzhimanhua.github.io/papers/www22zhang.pdf)][[Code](https://github.com/yuzhimanhua/MICoL)], 2022.2, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

6. **LinkBERT: Pretraining Language Models with Document Links.** `ACL 2022`

    *Michihiro Yasunaga, Jure Leskovec, Percy Liang.* [[Paper](https://arxiv.org/pdf/2203.15827.pdf)][[Code]](https://github.com/michiyasunaga/LinkBERT), 2022.3, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

7. **E2EG: End-to-End Node Classification Using Graph Topology and Text-based Node Attributes.** `ICDM 2023`

    *Tu Anh Dinh, Jeroen den Boef, Joran Cornelisse, Paul Groth.* [[PDF](https://arxiv.org/pdf/2208.04609.pdf)], 2022.8, ![](https://img.shields.io/badge/Encoder-blue) ![](https://img.shields.io/badge/Medium-red)

8. **TwHIN-BERT: A Socially-Enriched Pre-trained Language Model for Multilingual Tweet Representations at Twitter.** `KDD 2023`

    *Xinyang Zhang, Yury Malkov, Omar Florez, Serim Park, Brian McWilliams, Jiawei Han, Ahmed El-Kishky.* [[PDF](https://arxiv.org/abs/2209.07562)] [[Code](https://github.com/xinyangz/TwHIN-BERT)], 2022.9, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

9. **TouchUp-G: Improving Feature Representation through Graph-Centric Finetuning.** `preprint`

    *Jing Zhu, Xiang Song, Vassilis N. Ioannidis, Danai Koutra, Christos Faloutsos.* [[PDF](https://arxiv.org/abs/2309.13885)], 2023.9, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)


### <img src="./star.svg" width="15" height="15" /> LLM as Encoder
#### Optimization

1. **GNN-LM: Language Modeling based on Global Contexts via GNN.** `ICLR 2022`

    *Yuxian Meng, Shi Zong, Xiaoya Li, Xiaofei Sun, Tianwei Zhang, Fei Wu, Jiwei Li.* [[PDF](https://arxiv.org/abs/2110.08743)] [[Code](https://github.com/ShannonAI/GNN-LM)], 2021.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

2. **Node Feature Extraction by Self-Supervised Multi-Scale Neighborhood Prediction.** `ICLR 2022`

    *Eli Chien, Wei-Cheng Chang, Cho-Jui Hsieh, Hsiang-Fu Yu, Jiong Zhang, Olgica Milenkovic, Inderjit S Dhillon.* [[Paper](https://arxiv.org/pdf/2111.00064.pdf)][[Code](https://github.com/amzn/pecos/tree/mainline/examples/giant-xrt)], 2021.11, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

3. **TextGNN: Improving Text Encoder via Graph Neural Network in Sponsored Search.** `WWW 2021`

    *Jason Yue Zhu, Yanling Cui, Yuming Liu, Hao Sun, Xue Li, Markus Pelger, Tianqi Yang, Liangjie Zhang, Ruofei Zhang, Huasha Zhao.* [[PDF](https://arxiv.org/pdf/2101.06323.pdf)] [[Code](https://github.com/microsoft/TextGNN)], 2022.1

4. **AdsGNN: Behavior-Graph Augmented Relevance Modeling in Sponsored Search.** `SIGIR 2021`

    *Chaozhuo Li, Bochen Pang, Yuming Liu, Hao Sun, Zheng Liu, Xing Xie, Tianqi Yang, Yanling Cui, Liangjie Zhang, Qi Zhang.* [[PDF](https://arxiv.org/pdf/2104.12080.pdf)] [[Code]()], 2022.4

5. **Efficient and effective training of language and graph neural network models.** `AAAI 2023`

    *Vassilis N Ioannidis, Xiang Song, Da Zheng, Houyu Zhang, Jun Ma, Yi Xu, Belinda Zeng, Trishul Chilimbi, George Karypis.* [[Paper](https://arxiv.org/abs/2206.10781)], 2022.6, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

6. **Graph-Aware Language Model Pre-Training on a Large Graph Corpus Can Help Multiple Graph Applications.** `KDD 2023`

    *Han Xie, Da Zheng, Jun Ma, Houyu Zhang, Vassilis N. Ioannidis, Xiang Song, Qing Ping, Sheng Wang, Carl Yang, Yi Xu, Belinda Zeng, Trishul Chilimbi.* [[Paper](https://arxiv.org/pdf/2306.02592.pdf)], 2023.6, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

7. **Exploring the Potential of Large Language Models (LLMs) in Learning on Graphs.** `preprint`

    *Zhikai Chen, Haitao Mao, Hang Li, Wei Jin, Hongzhi Wen, Xiaochi Wei, Shuaiqiang Wang, Dawei Yin, Wenqi Fan, Hui Liu, Jiliang Tang.* [[PDF](https://arxiv.org/abs/2307.03393)] [[Code](https://github.com/CurryTang/Graph-LLM)], 2023.7, ![](https://img.shields.io/badge/EncoderOnly-blue)![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/Medium-red) ![](https://img.shields.io/badge/LLM-red)

8. **SimTeG: A Frustratingly Simple Approach Improves Textual Graph Learning.** `preprint`

    *Keyu Duan, Qian Liu, Tat-Seng Chua, Shuicheng Yan, Wei Tsang Ooi, Qizhe Xie, Junxian He.* [[PDF](https://arxiv.org/pdf/2308.02565.pdf)] [[Code](https://github.com/vermouthdky/SimTeG)], 2023.8, ![](https://img.shields.io/badge/Encoder-blue) ![](https://img.shields.io/badge/Medium-red)


#### Data Augmentation
1. **Explanations as Features: LLM-Based Features for Text-Attributed Graphs.** `preprint`

    *Xiaoxin He, Xavier Bresson, Thomas Laurent, Adam Perold, Yann LeCun, Bryan Hooi.* [[PDF](https://arxiv.org/pdf/2305.19523.pdf)] [[Code](https://github.com/XiaoxinHe/TAPE)], 2023.5, ![](https://img.shields.io/badge/EncoderOnly-blue)![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/Medium-red) ![](https://img.shields.io/badge/LLM-red)

2. **Label-free Node Classification on Graphs with Large Language Models (LLMS).** `preprint`

    *Zhikai Chen, Haitao Mao, Hongzhi Wen, Haoyu Han, Wei Jin, Haiyang Zhang, Hui Liu, Jiliang Tang.* [[PDF](https://arxiv.org/pdf/2310.04668.pdf)], 2023.9, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

3. **Empower Text-Attributed Graphs Learning with Large Language Models (LLMs).** `preprint`

    *Jianxiang Yu, Yuxiang Ren, Chenghua Gong, Jiaqi Tan, Xiang Li, Xuecang Zhang.* [[PDF](https://arxiv.org/pdf/2310.09872.pdf)], 2023.10, ![](https://img.shields.io/badge/EncoderOnly-blue)![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)![](https://img.shields.io/badge/LLM-red)

3. **Large Language Models as Topological Structure Enhancers for Text-Attributed Graphs.** `preprint`

    *Shengyin Sun, Yuxiang Ren, Chen Ma, Xuecang Zhang.* [[PDF](https://arxiv.org/pdf/2311.14324.pdf)], 2023.11, ![](https://img.shields.io/badge/EncoderOnly-blue)![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)![](https://img.shields.io/badge/LLM-red)


#### Knowledge Distillation
1. **Train Your Own GNN Teacher: Graph-Aware Distillation on Textual Graphs.** `PKDD 2023`

    *C. Mavromatis, V. N. Ioannidis, S. Wang, D. Zheng, S. Adeshina, J. Ma, H. Zhao, C. Faloutsos, G. Karypis.* [[Paper](https://arxiv.org/abs/2304.10668)], 2023.4, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

### <img src="./star.svg" width="15" height="15" /> LLM as Aligner (Node)
#### Prediction Alignment

1. **Minimally-Supervised Structure-Rich Text Categorization via Learning on Text-Rich Networks.** `WWW 2021`

    *Xinyang Zhang, Chenwei Zhang, Luna Xin Dong, Jingbo Shang, Jiawei Han.* [[PDF](https://arxiv.org/abs/2102.11479)] [[Code](https://github.com/xinyangz/ltrn)], 2021.2, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

2. **Learning on Large-scale Text-attributed graphs via variational inference.** `ICLR 2023`

    *Jianan Zhao, Meng Qu, Chaozhuo Li, Hao Yan, Qian Liu, Rui Li, Xing Xie, Jian Tang.* [[Paper](https://openreview.net/pdf?id=q0nmYciuuZN)][[Code](https://github.com/AndyJZhao/GLEM)], 2023.1, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)


#### Latent Space Alignment (Node)

1. **ConGraT: Self-Supervised Contrastive Pretraining for Joint Graph and Text Embeddings.** `preprint`

    *William Brannon, Suyash Fulay, Hang Jiang, Wonjune Kang, Brandon Roy, Jad Kabbara, Deb Roy.* [[PDF](https://arxiv.org/abs/2305.14321)] [[Code](https://github.com/wwbrannon/congrat)], 2023.5, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

2. **Augmenting Low-Resource Text Classification with Graph-Grounded Pre-training and Prompting.** `SIGIR 2023`

    *Zhihao Wen, Yuan Fang.* [[PDF](https://arxiv.org/abs/2305.03324)], 2023.5, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

3. **GRENADE: Graph-Centric Language Model for Self-Supervised Representation Learning on Text-Attributed Graphs.** `EMNLP 2023`

    *Yichuan Li, Kaize Ding, Kyumin Lee.* [[Paper](https://arxiv.org/abs/2310.15109)][[Code]](https://github.com/bigheiniu/GRENADE), 2023.10, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

4. **Pretraining Language Models with Text-Attributed Heterogeneous Graphs.** `preprint`

    *Tao Zou, Le Yu, Yifei HUANG, Leilei Sun, Bowen Du.* [[PDF](https://arxiv.org/pdf/2310.12580.pdf)] [[Code](https://github.com/Hope-Rita/THLM)], 2023.10, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)


## Text-Paired Graphs (Molecules)

### <img src="./star.svg" width="15" height="15" /> Datasets
Table 8 in our survey paper [Large Language Models on Graphs: A Comprehensive Survey](https://arxiv.org/abs/2312.02783).
<p align="center">
    <img src="./graph-data.jpg" width="90%" style="align:center;"/>
</p>

### <img src="./star.svg" width="15" height="15" /> LLM as Predictor (Graph)
#### Graph As Sequence


1. **SMILES-BERT: Large Scale Unsupervised Pre-Training for Molecular Property Prediction** `BCB 19`
    
    *Sheng Wang , Yuzhi Guo , Yuhong Wang , Hongmao Sun , Junzhou Huang* [[PDF](https://par.nsf.gov/servlets/purl/10168888)] [[Code](https://github.com/uta-smile/SMILES-BERT)], 2019.09, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

2. **MolGPT: Molecular Generation Using a Transformer-Decoder Model.** `Journal of Chemical Information and Modeling`
    
    *Viraj Bagal, Rishal Aggarwal, P. K. Vinod, and U. Deva Priyakumar* [[PDF](https://pubs.acs.org/doi/10.1021/acs.jcim.1c00600)] [[Code](https://github.com/devalab/molgpt)], 2021.10, ![](https://img.shields.io/badge/DecoderOnly-blue), ![](https://img.shields.io/badge/Medium-red)

3. **A Deep-learning System Bridging Molecule Structure and Biomedical Text with Comprehension Comparable to Human Professionals.** `Nature Communications`
    
    *Zheni Zeng, Yuan Yao, Zhiyuan Liu, Maosong Sun* [[PDF](https://www.nature.com/articles/s41467-022-28494-3)] [[Code](https://github.com/thunlp/KV-PLM)], 2022.02, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

4. **Chemformer: a pre-trained transformer for computational chemistry** `Machine Learning: Science and Technology`
    
    *Ross Irwin, Spyridon Dimitriadis, Jiazhen He and Esben Jannik Bjerrum* [[PDF](https://iopscience.iop.org/article/10.1088/2632-2153/ac3ffb/meta)] [[Code](https://github.com/MolecularAI/Chemformer)], 2022.02, ![](https://img.shields.io/badge/EncoderDecoder-blue) ![](https://img.shields.io/badge/Medium-red)

5. **Large-Scale Distributed Training of Transformers for Chemical Fingerprinting.** `Journal of Chemical Information and Modeling`
    
    *Hisham Abdel-Aty, Ian R. Gould* [[PDF](https://pubs.acs.org/doi/full/10.1021/acs.jcim.2c00715)] [[Code](https://github.com/GouldGroup/MFBERT)], 2022.06, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

6. **Galactica: A Large Language Model for Science** `Preprint`
    
    *Ross Taylor, Marcin Kardas, Guillem Cucurull, Thomas Scialom, Anthony Hartshorn, Elvis Saravia, Andrew Poulton, Viktor Kerkez, Robert Stojnic* [[PDF](https://arxiv.org/pdf/2211.09085)] [[Code](https://github.com/paperswithcode/galai)], 2022.11, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

7. **Translation between Molecules and Natural Language.** `EMNLP 2022`
    
    *Carl Edwards, Tuan Lai, Kevin Ros, Garrett Honke, Kyunghyun Cho, Heng Ji.* [[PDF](https://arxiv.org/pdf/2204.11817.pdf)] [[Code](https://github.com/blender-nlp/MolT5)], 2022.12, ![](https://img.shields.io/badge/EncoderDecoder-blue) ![](https://img.shields.io/badge/Medium-red)

8.  **Unifying Molecular and Textual Representations via Multi-task Language Modelling** `ICML 2023`
    
    *Dimitrios Christofidellis, Giorgio Giannone, Jannis Born, Ole Winther, Teodoro Laino, Matteo Manica* [[PDF](https://arxiv.org/pdf/2301.12586.pdf)] [[Code](https://github.com/gt4sd/multitask_text_and_chemistry_t5)], 2023.05, ![](https://img.shields.io/badge/EncoderDecoder-blue) ![](https://img.shields.io/badge/Medium-red)

9.  **What can Large Language Models do in chemistry? A comprehensive benchmark on eight tasks.** `NeurIPS 2023`  
   
    *Taicheng Guo, Kehan Guo, Bozhao Nan, Zhenwen Liang, Zhichun Guo, Nitesh V. Chawla, Olaf Wiest, Xiangliang Zhang* [[PDF](https://arxiv.org/pdf/2305.18365.pdf)] [[Code](https://github.com/chemfoundationmodels/chemllmbench)], 2023.9, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

10. **MolXPT: Wrapping Molecules with Text for Generative Pre-training.** `ACL 2023`

    *Zequn Liu, Wei Zhang, Yingce Xia, Lijun Wu, Shufang Xie, Tao Qin, Ming Zhang, Tie-Yan Liu.* [[PDF](https://arxiv.org/pdf/2305.10688)], 2023.05, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)


11. **Interactive Molecular Discovery with Natural Language** `preprint`
   
    *Zheni Zeng, Bangchen Yin, Shipeng Wang, Jiarui Liu, Cheng Yang, Haishen Yao, Xingzhi Sun, Maosong Sun, Guotong Xie, Zhiyuan Liu.* [[PDF](https://arxiv.org/pdf/2306.11976)] [[Code](https://github.com/JinyuanSun/ChatMol)], 2023.06, ![](https://img.shields.io/badge/EncoderDecoder-blue) ![](https://img.shields.io/badge/Medium-red)

12. **Empowering Molecule Discovery for Molecule-Caption Translation with Large Language Models: A ChatGPT Perspective** `preprint`
   
    *Jiatong Li, Yunqing Liu, Wenqi Fan, Xiao-Yong Wei, Hui Liu, Jiliang Tang, Qing Li.* [[PDF](https://arxiv.org/pdf/2306.06615)], 2023.06, [[Code](https://github.com/phenixace/MolReGPT)], ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

13. **Regression Transformer enables concurrent sequence regression and generation for molecular language modelling** `Nature Machine Intelligence`
   
    *Jannis Born, Matteo Manica* [[PDF](https://www.nature.com/articles/s42256-023-00639-z)] [[Code](https://github.com/IBM/regression-transformer)], 2023.6, ![](https://img.shields.io/badge/DecoderOnly-blue), ![](https://img.shields.io/badge/Medium-red)

14. **Can Large Language Models Empower Molecular Property Prediction?** `preprint`
   
    *Chen Qian, Huayi Tang, Zhirui Yang, Hong Liang, Yong Liu.* [[PDF](https://browse.arxiv.org/pdf/2307.07443.pdf)] [[Code](https://github.com/ChnQ/LLM4Mol)], 2023.7, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

15. **Mol-Instructions: A Large-Scale Biomolecular Instruction Dataset for Large Language Models** `preprint`
   
    *Yin Fang, Xiaozhuan Liang, Ningyu Zhang, Kangwei Liu, Rui Huang, Zhuo Chen, Xiaohui Fan, Huajun Chen* [[PDF](https://arxiv.org/pdf/2306.08018)], 2023.07, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

16. **GPT-MolBERTa: GPT Molecular Features Language Model for molecular property prediction.** `preprint`
   
    *Balaji, Suryanarayanan, Rishikesh Magar, and Yayati Jadhav.* [[PDF](https://arxiv.org/pdf/2310.03030.pdf)], 2023.10, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)


#### Graph-Empowered LLM (Graph)

1. **Text2Mol: Cross-Modal Molecule Retrieval with Natural Language Queries.** `EMNLP 2021`
   
    *Carl Edwards, ChengXiang Zhai, Heng Ji.* [[PDF](https://aclanthology.org/2021.emnlp-main.47.pdf)] [[Code](https://github.com/cnedwards/text2mol)], 2021.10, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

2. **GIMLET: A Unified Graph-Text Model for Instruction-Based Molecule Zero-Shot Learning.** `preprint`
   
    *Haiteng Zhao, Shengchao Liu, Chang Ma, Hannan Xu, Jie Fu, Zhi-Hong Deng, Lingpeng Kong, Qi Liu.* [[PDF](https://arxiv.org/abs/2306.13089)] [[Code](https://github.com/zhao-ht/GIMLET)], 2023.6, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

3. **Prot2Text: Multimodal Protein's Function Generation with GNNs and Transformers** `preprint`
   
    *Hadi Abdine, Michail Chatzianastasis, Costas Bouyioukos, Michalis Vazirgiannis* [[PDF](https://arxiv.org/pdf/2307.14367)], 2023.07, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

4. **ReLM: Leveraging Language Models for Enhanced Chemical Reaction Prediction.** `EMNLP 2023`
   
    *Yaorui Shi, An Zhang, Enzhi Zhang, Zhiyuan Liu, Xiang Wang.* [[PDF](https://arxiv.org/pdf/2310.13590.pdf)] [[Code](https://github.com/syr-cn/relm)], 2023.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)



### <img src="./star.svg" width="15" height="15" /> LLM as Aligner (Graph)

#### Latent Space Alignment (Graph)

1.  **A Molecular Multimodal Foundation Model Associating Molecule Graphs with Natural Language.** `preprint`
   
    *Bing Su, Dazhao Du, Zhao Yang, Yujie Zhou, Jiangmeng Li, Anyi Rao, Hao Sun, Zhiwu Lu, Ji-Rong Wen* [[PDF](https://arxiv.org/pdf/2209.05481.pdf)] [[Code](https://github.com/bingsu12/momu)], 2022.09, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

2. **Multi-modal Molecule Structure-text Model for Text-based Retrieval and Editing.** `preprint`
   
    *Shengchao Liu, Weili Nie, Chengpeng Wang, Jiarui Lu, Zhuoran Qiao, Ling Liu, Jian Tang, Chaowei Xiao, Anima Anandkumar* [[PDF](https://arxiv.org/pdf/2212.10789.pdf)], 2022.10, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

3. **Extracting Molecular Properties from Natural Language with Multimodal Contrastive Learning** `ICML 2023 Workshop on Computational Biology`
   
    *Romain Lacombe, Andrew Gaut, Jeff He, David Lüdeke, Kateryna Pistunova* [[PDF](https://arxiv.org/pdf/2307.12996)], 2023.07, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

4. **ProtST: Multi-Modality Learning of Protein Sequences and Biomedical Texts.** `ICML 2023`

    *Minghao Xu, Xinyu Yuan, Santiago Miret, Jian Tang.* [[PDF](https://arxiv.org/pdf/2301.12040.pdf)] [[Code](https://github.com/DeepGraphLearning/ProtST)], 2023.1, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)


5. **Enhancing Activity Prediction Models in Drug Discovery with the Ability to Understand Human Language.** `ICML 2023`

    *Philipp Seidl, Andreu Vall, Sepp Hochreiter, Günter Klambauer.* [[PDF](https://proceedings.mlr.press/v202/seidl23a/seidl23a.pdf)] [[Code](https://github.com/ml-jku/clamp)], 2023.5, ![](https://img.shields.io/badge/EncoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

6.  **MolFM: A multimodal molecular foundation model.** `Preprint`
   
    *Yizhen Luo, Kai Yang, Massimo Hong, Xing Yi Liu, Zaiqing Nie.* [[PDF](https://arxiv.org/pdf/2307.09484.pdf)] [[Code](https://github.com/PharMolix/OpenBioMed)], 2023.7, ![](https://img.shields.io/badge/EncoderDecoder-blue) ![](https://img.shields.io/badge/Medium-red)

7. **GIT-Mol: A Multi-modal Large Language Model for Molecular Science with Graph, Image, and Text** `Preprint`
   
    *Pengfei Liu, Yiming Ren, Zhixiang Ren* [[PDF](https://arxiv.org/pdf/2308.06911)], 2023.08, ![](https://img.shields.io/badge/EncoderDecoder-blue) ![](https://img.shields.io/badge/Medium-red)

8. **MolCA: Molecular Graph-Language Modeling with Cross-Modal Projector and Uni-Modal Adapter.** `EMNLP 2023`
   
    *Zhiyuan Liu, Sihang Li, Yanchen Luo, Hao Fei, Yixin Cao, Kenji Kawaguchi, Xiang Wang, Tat-Seng Chua.* [[PDF](https://arxiv.org/pdf/2310.12798v1.pdf)] [[Code](https://github.com/acharkq/MolCA)], 2023.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/Medium-red)

<!-- ## Language Modeling


2. **InstructProtein: Aligning Human and Protein Language via Knowledge Instruction.** `preprint`

    *Zeyuan Wang, Qiang Zhang, Keyan Ding, Ming Qin, Xiang Zhuang, Xiaotong Li, Huajun Chen.* [[PDF](https://arxiv.org/pdf/2310.03269v1.pdf)], 2023.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red)

## Question Answering


7. **ChatKBQA: A Generate-then-Retrieve Framework for Knowledge Base Question Answering with Fine-tuned Large Language Models.** `preprint`

    *Haoran Luo, Haihong E, Zichen Tang, Shiyao Peng, Yikai Guo, Wentai Zhang, Chenghao Ma, Guanting Dong, Meina Song, Wei Lin.* [[PDF](https://arxiv.org/pdf/2310.08975.pdf)] [[Code](https://github.com/lhrlab/chatkbqa)], 2023.10, ![](https://img.shields.io/badge/DecoderOnly-blue) ![](https://img.shields.io/badge/LLM-red) -->




## Contribution

Contributions to this repository are welcome!

If you find any error or have relevant resources, feel free to open an issue or a pull request.

Paper format:
```
1. **[paper title].** `[]`

    *[authors].* [[PDF]([pdf link])] [[Code]([code link])], published time, ![](https://img.shields.io/badge/[architecture]-blue) ![](https://img.shields.io/badge/[size]-red)
```

## Citations

Please cite the following paper if you find the resource helpful for your research.
```
@article{jin@llmgraph,
  title={Large Language Models on Graphs: A Comprehensive Survey},
  author={Jin, Bowen and Liu, Gang and Han, Chi and Jiang, Meng and Ji, Heng and Han, Jiawei},
  journal={arXiv preprint arXiv:2312.02783},
  year={2023}
}
```
