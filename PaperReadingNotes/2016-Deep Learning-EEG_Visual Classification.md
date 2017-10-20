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
#### 二、背景介绍   
>   尽管最近卷积神经网络(CNN)在自动视觉分类方面具有很好的性能提升，但他们的泛化能力还不能和人类比拟。因为学习可区分的特征空间严格依赖训练数据集而不是通用的准则，更特别地是，CNN的第一层特征在跨不同数据集似乎都通用(generalizable)，该层特征和Gabor滤波器和彩色斑点(color blobs)很相似；然而对于特别地数据集或任务，CNN的最后一层就变得非常specific。人类视觉分类则相反，人类视觉对象识别的过程建立在感知(即物体在形状，颜色等方面是如何以视觉方式出现的等，感知这块所有的特征都可以用CNN的第一层建模)和概念(包含从未被剥夺的更高级的认知过程)。一些认知神经科学研究发现视觉皮层部分和大脑和这些认知过程有关，但，迄今为止没有清晰的solution。当然，这折射了基于认知功能的自动视觉分类方法的困难性。   
> * * *
> 作者认为一个可能的解决方法是反向工程学的手段，通过分析由神经心理学(EEG/MEG)和神经影像学(如，fMRI)记录得到的人脑活动，通过使用人类视觉分类识别特征空间.理解特定刺激诱发得到的EEG数据是脑机接口(BCI)领域多年来的目标。脑机接口致力于分类或检测特定的脑信号，以允许残疾人能够直接控制机器。这篇文章想在经典的BCI研究方法基础上有跳跃式的改进，致力于探索human-based 计算策略进行自动视觉分类。这个过程主要分为两大过程：reading the mind，然后transfer human visual capabilities to machines。识别视觉categorization基于EEG的可区分的特征对理解人类视觉系统提供了新的观点，将极大改进BCI应用程序的性能，还有可能提供新的基于脑的图像标注形式。第二，有效地将图像投影到新的基于生物学的manifold中将会彻底改变对象分类器的开发方式（主要是在特征提取方面）。   
>* 基于深度学习分类视觉对象刺激诱发的EEG信号，在处理对象分类和准确率方面超出了state-of-the-art方法。   
>* 首次提出了脑信号驱动的计算机视觉方法。
>* 随后会公开发布最大的视觉对象分析的EEG数据库，包含相关的源代码和训练好的模型。   
#### 三、相关研究工作
> （1）P300 检测;    
> （2）癫痫检测；   
> （3）结合RNN和CNN来学习认知分类任务的EEG表征(报道的分类准确率在超过四个认知负荷水平上达到90%)；   
> （4）仅使用CNN，用来学习由音乐刺激诱发的EEG信号对音乐进行分类，12首歌的准确率为28%；   
> （5）许多认知神经科学研究(通过识别视觉皮层的特定区域)已经表明，可以在通过脑电图记录的事件相关电位(ERP)幅度解码多达十几对象类别。
#### 四、研究方法
> 本文的研究工作主要依赖以下三个关键的原型(intuition)：
>* 被试看图片传达的有关图片内容特征级和认知级的信息过程诱发的EEG信号被记录，两个不同的对象类给出的视觉刺激引起的EEG信号如图1所示：
![图1](https://github.com/YunTuring/deeplearning.github.io/blob/master/PaperReadingNotes/PaperPictures/2016-EEG-CNN-RNN.jpg)
>* 存在多维和随时间变化的EEG信号的低维manifold，并且可以提取以获得我们称为EEG特征的一维表征。   
>* 假设EEG特征主要编码视觉数据，因此可以提取相应的图像描述符进行自动分类。   
   
> 主要研究内容如图2所示：
![图2](https://github.com/YunTuring/deeplearning.github.io/blob/master/PaperReadingNotes/PaperPictures/2016_EEG-RNN-CNN-framework.jpg)
> 1. 第一阶段——reading the mind，旨在识别两维(channel和time)脑电空间的低维度流形(manifold)，使得该manifold内的表征符合对象类别。为了学习这些表征，作者记录当被试看屏幕上的图片的脑电信号，然后训练一个编码器网络(使用循环神经网络(RNN)——为了分析时间信息)，从原始脑电信号中提取脑电特征；训练过程由记录的每个输入的脑电序列的图像类监督，并且该过程和用于脑电特征分类的分类器联合训练。   
> 2. 第二阶段——transfer human visual capability to machines，通过学习从CNN深度视觉描述符到脑电图特征的映射(mapping)，之后，通过训练好的基于CNN的回归估计器，来简单地估计其脑电特征，来分类新的图像，使用一级分类器来预测相应的图像类别。
#### 获取脑电数据
> 实验记录了六名被试(5男，1女)的脑电数据，被试在年龄、受教育水平和文化背景等方便都由专业心理学家评估，以排除可能干扰实验的状况(比如，疾病)。使用的视觉刺激图片来自于ImageNet的子集，包含很容易识别的40种类的物体(狗、猫、蝴蝶、大象、熊猫、电脑、吉他、鱼、自行车、高尔夫、收音机、相机、香蕉等)。使用BP公司的128通道的脑电设备采集数据，采样率为1000Hz，数据分辨率为16bit，对信号进行了陷波滤波[49-51Hz]，排除50Hz工频干扰，然后用二阶Butterworth带通滤波(低频截止频率为14Hz，高频截止频率为71Hz)，保留Beta波[15-31HZ]和Gamma[32-70]波段，因为这两个波段被认为能传达视觉认知处理过程的一些信息。丢弃每个图片呈现的前40秒数据以排除可能的干扰。具体实验范式参考表1：   
> ![表1](https://github.com/YunTuring/deeplearning.github.io/blob/master/PaperReadingNotes/PaperPictures/2016-EEG-CNN-RNN-Protocol.jpg)
#### 学习脑电manifold
> 首要方法旨在将输入的多通道脑电序列降维至低维特征向量(能涵盖输入序列的相关内容)。作者提到先前的降维方法只是简单地将多个通道的时间序列拼接成单个特征向量，忽视了时间动力学，而这恰恰是理解脑电活动的基本信息。为了包含这些时间动力学特性，我们使用LSTM循环神经网络(因为它能够track输入数据长时间的依赖性)。EEG多通道时间信号，如第3节所述进行预处理。 3.1作为输入提供给编码器模块，该编码器模块处理整个时间序列并输出EEG特征向量作为输入的紧凑表示。 理想情况下，如果输入序列由观看图像时记录的EEG信号组成，则我们的目标是使得到的输出向量编码相关的大脑活动信息，以区分不同的图像类别。 编码器网络通过在其输出处加入分类模块（在我们的所有实验中将是softmax层），并使用梯度下降来在端对端学习整个模型的参数。   
在本文的实验中，作者测试了编码器网络的几种配置：   
> （1）*Common LSTM*   
> （2）*Channel LSTM* + *Common LSTM*   
> （3）*Common LSTM* + *output layer*
![图3]()
#### 基于CNN的回归器对脑电manifold进行视觉分类
> 本文采用两种基于CNN的方法来从一幅输入图像中提取脑电特征：
>* 方法1：
>* 方法2：
![图4]()
#### 五、性能分析   
> 请参考论文(此处省略)   
#### 六、讨论
> 略
