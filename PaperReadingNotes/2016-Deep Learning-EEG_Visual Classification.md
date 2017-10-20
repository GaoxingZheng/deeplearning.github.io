#### Paper Title : "Deep Learning Human Mind for Automated Visual Classification"  
#### Paper website : https://arxiv.org/abs/1609.00344  
@YunTuring, zheng_gao_xing@163.com;    
>*Markdown生成水平分割线：可以单独一行里输入3个或以上的短横线（减号）、星号或者下划线实现。短横线和星号之间可以任意空格。*   
#### 一、摘要   
> 如果我们能够有效地阅读思维(read the mind)并将人类视觉能力迁移到计算机视觉方法上会怎么样？在本文中，
我们旨在通过开发人脑信号驱动的第一个视觉对象分类器来解决这个问题。特别地，我们采用与循环神经网络(RNN)结合的视觉对象刺激诱发EEG数据，
在阅读思维的努力中学习视觉类别的辨别性脑活动manifold。之后，我们通过训练基于卷积神经网络(CNN)的回归器将学习的能力迁移到机器上，
将图像投影到学习的多维数据集上(project images onto the learned manifold)，从而允许机器采用基于人脑的特征来进行自动视觉分类，
我们使用128通道电极的EEG来记录不同被试在看40个ImageNet对象类图像的脑活动，使用脑信号识别对象类的基于RNN的方法平均精度约为83%，
这大大优于现有的试图学习EEG视觉对象表征方法。对于自动对象分类，人脑驱动的方法获得了竞争优势，与强大的CNN模型所实现的性能相当，
并且还能够将不同的视觉数据集进行推广。
>* * *
> What if we could effectively read the mind and transfer human visual capabilities to computer vision methods? In this paper, we aim at addressing this question by developing the first visual object classifier driven by human brain signals. In particular, we employ EEG data evoked by visual object stimuli combined with Recurrent Neural Networks (RNN) to learn a discriminative brain activity manifold of visual categories in a reading the mind effort. Afterward, we transfer the learned capabilities to machines by training a Convolutional Neural Network (CNN)–based regressor to project images onto the learned manifold, thus allowing machines to employ human brain–based features for automated visual classification. We use a 128-channel EEG with active electrodes to record brain activity of several subjects while looking at images of 40 ImageNet object classes. The proposed RNN-based approach for discriminating object classes using brain signals reaches an average accuracy of about 83%, which greatly outperforms existing methods attempting to learn EEG visual object representations. As for automated object categorization, our human brain–driven approach obtains competitive performance, comparable to those achieved by powerful CNN models and it is also able to generalize over different visual datasets.
>- - - 
二、背景介绍   
> 尽管最近卷积神经网络(CNN)在自动视觉分类方面具有很好的性能提升，但他们的泛化能力还不能和人类比拟。因为学习可区分的特征空间严格依赖训练数据集而不是通用的准则，更特别地是，CNN的第一层特征在跨不同数据集似乎都通用(generalizable)，该层特征和Gabor滤波器和彩色斑点(color blobs)很相似；然而对于特别地数据集或任务，CNN的最后一层就变得非常specific。人类视觉分类则相反，人类视觉对象识别的过程建立在感知(即物体在形状，颜色等方面是如何以视觉方式出现的等，感知这块所有的特征都可以用CNN的第一层建模)和概念(包含从未被剥夺的更高级的认知过程)。一些认知神经科学研究发现视觉皮层部分和大脑和这些认知过程有关，但，迄今为止没有清晰的solution。当然，这折射了基于认知功能的自动视觉分类方法的困难性。   
 作者认为一个可能的解决方法是反向工程学的手段，通过分析由神经心理学(EEG/MEG)和神经影像学(如，fMRI)记录得到的
