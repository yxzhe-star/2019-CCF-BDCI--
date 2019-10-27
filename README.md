# 2019-CCF-BDCI
本人是初学者。本篇文章主要是开源比赛的代码，并记录一些自己学到的知识，首先感谢一些大佬在比赛前期的开源，使我能快速入门赛题。
# 比赛说明
2019-CCF-BDCI 互联网金融新实体发现。比赛地址：https://www.datafountain.cn/competitions/361 
随着互联网的飞速进步和全球金融的高速发展，金融信息呈现爆炸式增长。投资者和决策者在面对浩瀚的互联网金融信息时常常苦于如何高效的获取需要关注的内容。针对这一问题，金融实体识别方案的建立将极大提高金融信息获取效率，从而更好的为金融领域相关机构和个人提供信息支撑。
# 比赛结果
# 运行环境
## 环境  
腾讯云ti-one  
python 3.5  
tensorflow 1.12  
## 硬件  
tesla P40, 大约需要12g显存。如果没有大显存，调小maxlen和batch size即可，可能效果会略有下降  
## 运行  
修改各种路径，直接run.sh就可以了。
# 模型（bert+bilstm+crf）
本题是自然语言处理的ner（命名实体识别）问题，ner本质其实也是分类问题，只不过是token级别的分类。  
在bert模型出来前，主流的解决方法是将词向量输入bilstm+crf来分类。不过google去年开源了bert之后，nlp的许多任务准确率大幅提升。自然ner也不例外，只不过bert在ner中相当于充当词向量，后续一样。不过google开源的源码里好像没有ner任务，此处参考大佬改写的bert ner版：https://github.com/jiangxinyang227/NLP-Project（真的是大佬，将各类任务都改写了一遍）。
