---
title: Guide for beginners to bioinformatics
authors:
- huyichen
subtitle:
summary:
tags: ['guide']
categories: []
date: "2019-12-07T00:00:00Z"
lastmod: "2020-07-28"
featured: false
draft: false
---

<br/><br/>
以下为开启生物信息学习的简易入门教程及小贴士，仅供参考。

# **LINUX**

## 推荐书籍

阅读原则：第一遍阅读快速浏览，熟悉命令行。大概记住常用命令的使用，实际使用时知道应该调用哪个命令。

1. “The Linux Command Line” by [William Shotts](http://linuxcommand.org/tlcl.php)
2. “Learn Linux the Hardway” by Shaw
3. [中文教程推荐《鸟哥的Linux私房菜》](http://cn.linux.vbird.org/)

<br/>

# **PYTHON**

## 推荐书籍

阅读原则：达到能够写class的程度

2.  “Python Crash Course” 适合初学者，但内容略简单
3.  “Learning Python, 5th Edition” by Mark Lutz 比较适合系统学习（推荐）
3.  “Python Cookbook(3rd Edition)” by O'Reilly 不太适合初学者
4.  “Fluent Python” 进阶学习
5.  [Python 100 days](https://github.com/jackfrued/Python-100-Days)

<br/>

# **[QIIME2](https://qiime2.org/)**

详细内容请自行浏览qiime2网站，以下为一些经验建议：

-   安装：如在windows系统下，建议先安装虚拟机，在虚拟机上装linux系统，再安装qiime2。注意是qiime2，不是qiime。
-   tutorials：重点熟悉“Moving Pictures”，搞清楚每一步是做什么，得到的文件又是什么意思。
-   查看命令：第一次跑tutorial时，通过help查看命令每个参数的意思。
-   qiime2 [Aritface API](https://docs.qiime2.org/2020.6/interfaces/artifact-api/)可在Jupyter Notebook中使用。
-   在查看qiime tutorial时，注意版本，需与你安装的版本一致。以下内容适用于qiime2 version 2018.11，如果是其他版本，可能有所出入。

## Moving Pictures

1.  metadata/mapping file
    -   metadata记录原始数据，样本信息等，metadata需为tsv格式。
    -   metadata第一列名应为sampleid，注意sampleid列中的样本名不可以含有下划线（deblur DOESN'T support sample IDs with underscores, including the sample IDs in your metadata and sequence files, or your manifest file)
    -   metadata的要求请参照[Metadata in QIIME 2](https://docs.qiime2.org/2019.10/tutorials/metadata/)
2.  sequence files
    -   序列文件通常为fastq/fna格式，less可查看，gz文件用zless查看。
    -   序列文件是已经去掉了barcode/primer/adaptor的clean data。
    -   demux后的序列文件通过提供manifest来导入，注意不同日期批次的qiime2在menifast格式上可能存在区别，所以一定要确认你正在使用的qiime2的版本。
    -   注意:所有的序列都应该测的是同一段区域（起点相同），序列之间才具有可比性，否则序列比对是没有意义的。
3.  barcode files
    -   barcode用来区别该序列来自于哪个样本，类似于商品的条形码。来自同一个样本的序列用相同barcode标记，所以根据barcode可以知道哪条序列属于哪个样本。
4.  demultiplex
    -   根据barcode信息，判断sequence是来自哪个样本，从而得到每个样本含有哪些序列，有多少序列。
    -   如为反向互补序列，demux时选择参数&#x2013;p-rev-comp-mapping-barcodes。
5.  quality control
    -   推荐deblur:[deblur](http://msystems.asm.org/content/2/2/e00191-16)较传统的OTU聚类的方法，可以得到更精确的亚OTUs的信息。该方法是分别对单个样本进行分析，当样本来自不同批次或不同数据集时，该方法同样适用。
    -   如果input是paired end sequence data，在deblur时实际上只会用到正向序列，而不会用到反向序列。如有需要用到反向序列，可[join reads](https://docs.qiime2.org/2019.4/tutorials/read-joining/)。
    -   qiime deblur denoise-16S 需要注意的参数：
        (a) &#x2013;p-no-hashed-feature-ids 即保留原始序列（ATGC格式）。
        (b) &#x2013;p-min-reads
        (c) 查看deblur.qzv：理论上deblur之后剩下的序列数为(1-error rate)\*\*trim length（其中error rate=0.005）；以100个碱基长度为例，deblur之后剩下的序列>(1-0.005)\*\*100才比较合理
6.  generate a tree
    -   moving picture中介绍了rooted tree
    -   其他建树的方法有fragment insertion sepp
7.  diversity analysis
    -   参数&#x2013;p-sample-depth的选择，可参考rarefaction curve，选择曲线上升到平台期为宜。
    -   diversity的分析前，不要忘记对table做rarefy！rarefaction的意义在于，当抽样深度不同时，rarefaction使不同测序深度间变得有可比性。
    -   alpha diversity: how many kinds of microbes are there单个样本内含有多少微生物。可从以下几个方面比较：（1）richness 种类（例如2个样本，1号含100种微生物，2号含150种微生物，这里只考虑种类，不考虑数量）；（2）evenness 均匀度（例如2个样本，1号含A3B3C3,2号A1B1C7，字母代表不同的OTU，数字代表个数，那么这个例子中1号OTU分布显然比2号更均匀）。常用计算alpha div的方法有：（1）observed otus (richness) 只计算每个样本中otu的种类；（2）evenness (evenness) 解释见上；（3）shannon (richness + evenness) 既考虑种类又考虑均匀度；（4）simpson (richness + evenness) 同上；（5）faith's phylogenetic distance 除了还考虑种类和均匀度，还考虑进化距离……
    -   beta diversity: similarity and dissimilarity between two different samples两个样本间的相似性或不同
    -   在coursera课程[Gut Check: Exploring Your Microbiome](https://www.coursera.org/learn/microbiome)中，有关于diversity有生动的说明，请自行移步。另外可参考[Studying Microbial Diversity](http://readiab.org/book/0.1.3/3/1#4.1.2)。
8.  taxonomy assignment
    -   根据实际情况，可选择用pre-trained Naive Bayes classifier ;如不适用，可根据自己的primer来[train classfier](https://docs.qiime2.org/2019.4/tutorials/feature-classifier/)。
    -   qiime feature-classifier classify-sklearn &#x2013;p-read-orientation [reverse-complement|same]默认是自动检测前100个bases，然后判断是reverse还是same，一般默认参数就行。
9.  ANCOM：得到差异表达的OTU
    -   ancom默认进行比较的两组样本是相互独立的，且仅有少量的（少于25%）的OTUs在两组间发生了改变。如果有大量序列改变，则不适用。
    -   其他differential abundance计算方法还有q2-aldex2, q2-songbird, q2-conrcob等。

## Importing Data

-   tsv, csv, txt文件可转化成[The Biological Observation Matrix (BIOM) format](http://biom-format.org/documentation/biom_conversion.html)再导入。

## Emperor Animation

-   emperor可实现动画：在[qiime2 view](https://view.qiime2.org/)中打开emperor.qzv文件，右侧栏选择animation列，选择gradient（时间轴上的分组）和trajectory（样本的分组）category（它们的value必须是分类值，不能是数值）。

## Tips

-   查看tutorial时需注意当前版本，应与安装的版本相对应（tutorial页面最左有版本信息），否则有些代码时可能会出现报错。
-   命名不要有空格和中文，不要取模棱两可的名字，时间久了可能自己都不记得这个文件是什么。名字长一点都没关系。
-   原则上不产生重复文件，可创建hard/symbolic link。
-   不要轻易覆盖raw data。
-   碰到解决不了的问题可在qiime2 forum上找是否有同样的问题，通常可以找到。或可以自己在上面提问。
-   所有command lines都要做好记录，要知道每一个文件是如何生成的，出现问题的时候能够追根溯源。同时，要记录好qiime2及其他工具的版本信息。
-   重要的文本文件用git做version control。
-   图片保存格式为pdf或者svg（矢量图）。
-   做项目时，一个项目创建一个文件夹，与该项目相关的文件都保存在该目录下。

<br/>

# **课程推荐**

## Data Analysis

-   经过学习以上部分，有了基础概念之后，跟着这个[网址](https://github.com/cuttlefishh/python-for-data-analysis)进行数据分析课程的学习
-   参考用书“Python for Data Analysis”，涉及pandas，numpy，matplotlib，seaborn&#x2026;

## Microbime

- [Gut Check: Exploring Your Microbiome](https://www.coursera.org/learn/microbiome)

<br/>

# **阅读推荐**

## 期刊

推荐阅读期刊：nature, science, cell, PNAS, nature communication, nature microbiology, microbiome, cell host & microbes, ISME journal, gut, Gastroenterology, Genome Research, mbio, msystems

## Tips

-   看文献时，abstract->fig->discussion
-   看文献时也要了解作者，通过作者去了解别人实验室的研究方向，可以学习别人实验上的思路/实验设计/延续性等。
-   带着批判性思维阅读what?why?and how? 为什么要做这个实验，数据是否支持结论，统计方法是否正确，你接下来会怎么做等。
-   在自己研究方向上进行阅读，形成知识架构。什么是已知的，什么的未知的，提出问题，多思考如何解决问题。
-   文献汇报选择与自己研究直接相关的文章，有助于自己文献阅读的连续性。
-   实验汇报用1套PPT，每次在之前的基础上积累完善。包括背景介绍，提出问题，如何解决，用什么方法解决，结果，下阶段的计划安排。

## 书籍

-   "I contain multitudes" by Ed Yong
-   "Missing Microbes" by Martin J. Blaser
-   [A primer for computational biology](http://library.open.oregonstate.edu/computationalbiology/)

<br/>

# **其他工具**

## calour

-   熟悉tutorial
-   得到otuTable后，通常会用calour工具进行一些探索性的分析，用calour工具可以非常方便地对data进行filtering。

## matplotlib/seaborn

- 最常用的画图工具，推荐教程： [matplotlib-tutorial](https://www.labri.fr/perso/nrougier/teaching/matplotlib/)

-   [mutipage pdf](https://matplotlib.org/gallery/misc/multipage_pdf.html) 可同时保存多张图片

## jupyter notebook/jupyterlab & ipython

-   Don't forget we can look at what any function does by using %psource
-   Don't hardcode。同一套代码写成function后调用。写function注意逻辑性。

## git commands

-   Github
    [hello world tutorial](https://guides.github.com/activities/hello-world/)
    [git and github](https://github.com/cuttlefishh/python-for-data-analysis/blob/master/lessons/lesson20.md)
-   Git commands
    [command-line fundamentals](https://www.youtube.com/watch?v=HVsySz-h9r4)（视频介绍）
-   重要的文件用git做version control，尤其是自己写的文本文件。了解简单的git add/commit/pull/push等命令的使用。

## coursera-dl

- coursera课程可通过coursera-dl命令进行下载，详见[coursera-dl github](https://github.com/coursera-dl/coursera-dl)。

