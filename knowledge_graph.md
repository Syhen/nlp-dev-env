[toc]

# 知识图谱的构建
[知识抽取-实体及关系抽取]("https://zhuanlan.zhihu.com/p/44772023")

简单的：三元组：实体（entity）、属性（property）、关系（relationship）

复杂一点的：图网络，每个实体还有他的属性，实体间的连接关系是变动的

人工干预可能会有很多

## 目标应用
- 应用：QA？检索？
- 精度要求？90%？
- 响应要求？50ms？

## 数据源
- 实体：百度百科的作为训练集、互动百科？
- 关系提取：百度百科详细文本
- 公司积累？
- 量级：量级多大？

## 主要流程

### 知识获取
#### 实体
  - 命名实体识别
    - Bi-LSTM + CRF or Bert + CRF or Bi-LSTM + Softmax
    - [推荐页面]("https://www.sohu.com/a/121246959_465975")
    - [Building a Fine-Grained Entity Typing System Overnight for a New X (X = Language, Domain, Genre), 2016]("https://arxiv.org/pdf/1603.03112.pdf")
    - [A Simple Semi-supervised Algorithm For Named Entity Recognition]("https://www.aclweb.org/anthology/W09-2208")
    - 无监督或半监督应该怎么做？
  - NER跑了之后需要人工审核
  - 爬虫爬取实体
    - [医疗健康有关实体]("https://baike.baidu.com/science/medical")
    - [互动百科-健康]("http://fenlei.baike.com/%E5%81%A5%E5%BA%B7/list/") 956个

#### 实体关系提取
  - [Attention-Based Convolutional Neural Network for Semantic Relation Extraction]("https://www.aclweb.org/anthology/C16-1238")
  - [Relationship Extraction from Unstructured Text Based on Stanford ...]("https://www.youtube.com/watch?v=PlmNvfyVy_4")
  - [Lecture 48 — Relation Extraction - Natural Language Processing ...]("https://www.youtube.com/watch?v=TbrlRei_0h8")

#### 事件知识学习
就是将非结构化文本中自然语言所表达的事件以结构化的形式呈现，对于知识表示、理解、计算和应用意义重大。

### 知识融合
#### 实体指代消歧
- 指代消歧
- 实体链接

#### schema融合
重要，常常可以考虑人工干预

### 知识表示

#### Embedding

#### RDF

### 知识推理

#### 知识补全

#### 知识去噪

#### 推理决策

## 存储
[Top 10 Database]("https://blog.csdn.net/hanyueqi/article/details/45245609")

### RDF
- GraphDB: Graph database and RDF triplestore built on OWL standards

### Graph Database
- Neo4j: py2neo
