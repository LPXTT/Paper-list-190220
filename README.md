# Paper-list-190415 


## Single Object Tracking
### SiamRPN 系列:
-----------------
[SiamRPN](http://openaccess.thecvf.com/content_cvpr_2018/papers/Li_High_Performance_Visual_CVPR_2018_paper.pdf)
将目标检测中的RPN技术引入SiameseFC中，取代最后交叉相关定位目标的部分。把原来单一的基于匹配的目标定位分为分类和定位两条支路，相比于原来的单一回归支路做定位会更加精准一些。至于它的速度（160fps）比原来的SiameseFC(80fps)快的原因，大概是去掉了原来三次计算来估计尺寸的方法，还有机器可能更好一些吧～

[Da-SiamRPN](http://openaccess.thecvf.com/content_ECCV_2018/papers/Zheng_Zhu_Distractor-aware_Siamese_Networks_ECCV_2018_paper.pdf)

[SiamRPN++](https://arxiv.org/pdf/1812.11703.pdf)

[CIR](https://arxiv.org/pdf/1901.01660.pdf)

[SiamMask](https://arxiv.org/pdf/1812.05050.pdf)

[C-RPN](https://arxiv.org/pdf/1812.06148.pdf)

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
