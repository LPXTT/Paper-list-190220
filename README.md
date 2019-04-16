# Paper-list-190415 


## Single Object Tracking

### SiamRPN 系列:
-----------------

[SiamRPN](http://openaccess.thecvf.com/content_cvpr_2018/papers/Li_High_Performance_Visual_CVPR_2018_paper.pdf)

将目标检测中的RPN技术引入SiameseFC中，取代最后交叉相关定位目标的部分。把原来单一的基于匹配的目标定位分为分类和定位两条支路，相比于原来的单一回归支路做定位会更加精准一些。至于它的速度（160fps）比原来的SiameseFC（80fps）快的原因，大概是去掉了原来三次计算来估计尺寸的方法，还有机器可能更好一些吧～

[Da-SiamRPN](http://openaccess.thecvf.com/content_ECCV_2018/papers/Zheng_Zhu_Distractor-aware_Siamese_Networks_ECCV_2018_paper.pdf)  
**出发点**：SiamRPN和SiameseFC的共同问题是，对类间干扰的抵抗能力差；通用表达空间与特别物体表达空间的不一致。  
**贡献**： a) Distractor-aware Training; b) Incremental Learning; c) Long-term  
在训练网络时引入了同类和不同类（来自不同视频目标）的负样本对，为扩大样本中所包含的物体类别数量，增加两个训练数据库，数据增广技巧有所改善。
选择最终目标框时，利用增量学习的方法。

[SiamRPN++](https://arxiv.org/pdf/1812.11703.pdf)  
**出发点**： 利用更加深层的网络；  
**贡献**：1）深层网络缺少位移不变性限制-->空间感知的采样策略（spatial aware sampling strategy)；2）layer-wise and depth-wise aggregations-->不同层特这融合提高精度，分解卷积操作减少模型参数  
**分析孪生网络特点**：  
深度网络无法在孪生目标跟踪算法中取得比较好的结果主要有两个原因：padding引入位移变化；RPN要求非对称特征做分类和回归。  
***针对padding引入的位移变化***： 空间感知采样，即在训练中引入图像位移，而不是全用以目标为中心的图像块训练，这是因为目标为中心的图像块训练出来的网络存在严重的位置偏见，它们趋于认为目标存在于中心位置。  
***RPN要求非对称特征做分类和回归***：DW-XCorr,两路特征先经过不同卷积层转换，然后做通道导向的卷积操作（即得到256通道而不是一通道的特征），然后再经过卷积层融合不同的通道做分类和回归。减少参数。

[CIR](https://arxiv.org/pdf/1901.01660.pdf)  
**出发点**： 利用更加深层的网络；  
**贡献**：1）新的参差模块(crop-inside residual-CIR）2）控制感受野和步长  
**影响深度网络应用的因素**：感受野、步长和补充（receptive field size, network stride and feature padding)  
                        1) 步长4或8比较合适  
                        2）感受野为原来输入目标图像的0.6-0.8较为合适  
                        3）padding 对最终效果有不好的影响 *原因在于：模板特征是原目标加padding部分，而搜索区域上对应匹配的图像块有的加padding                           部分，有的加背景图像部分;目标移动到图像边界时，顶峰无法反映目标位置* ？？应该影响不大吧。  

[SiamMask](https://arxiv.org/pdf/1812.05050.pdf)  
**出发点**：跟踪任务与分割任务放到一起去做。
**贡献**：孪生网络加分割（2个卷积层）支路。


### CVPR 2019:
-----------------

[C-RPN](https://arxiv.org/pdf/1812.06148.pdf)  
**贡献**： 多个RPN（训练层级删选难的负样本训练高层RPN，跟踪由粗到细优化目标框）；多层特征（特征转换模块融合不同特征）
**出发点**：  
1）SiamRPN对同类语义干扰不敏感原因：正负训练样本不匹配+大部分负样本为容易判别的负样本   
2）底层特征没有得到充分利用  



Tutorial
-----------------
[莫烦python](https://morvanzhou.github.io/tutorials/machine-learning/reinforcement-learning/)

[David Silver](https://space.bilibili.com/74997410/channel/detail?cid=53966) [[Slides]](http://www0.cs.ucl.ac.uk/staff/D.Silver/web/Teaching.html)

[UC Berkeley](https://www.bilibili.com/video/av32730838) [[Slides]](http://rail.eecs.berkeley.edu/deeprlcourse/)

[Deepmind](https://www.bilibili.com/video/av36621866) [[Slides]](http://www.cs.ucl.ac.uk/current_students/syllabus/compgi/compgi22_advanced_deep_learning_and_reinforcement_learning/)
[[github]](https://github.com/RylanSchaeffer/ucl-adv-dl-rl)

[李宏毅深度强化学习(国语)课程](https://www.bilibili.com/video/av24724071?from=search&seid=14814651069494196110) [[Slides]](http://speech.ee.ntu.edu.tw/~tlkagk/courses_MLDS18.html)

Codes
-------------------
[DeepMind](https://github.com/deepmind/trfl)

Githubs
--------------------------
[强化学习从入门到放弃的资料](https://github.com/wwxFromTju/awesome-reinforcement-learning-zh)
