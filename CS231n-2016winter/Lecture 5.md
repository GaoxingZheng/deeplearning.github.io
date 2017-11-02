
### Statement:    
> this reading notes summarized by @ChinaHQ, thanks for Feifei Li and his students transfer their knowledge to all over the world, thanks for Stanford University!
### Overview
#### 1. One time setup   
*activation functions, preprocessing, weight initialization, regularization, gradient checking*
#### 2. Training dynamics   
*babysitting the learning process, parameter updates, hyperparameter optimization*
#### 3. Evaluation   
*model ensembles*    

#### 一. Activation functions: 激活函数的作用增加非线性，这样深层神经网络才可以提取更多不同的特征。   
（1） Sigmoid；（2）tanh；（3）ReLU : max(0,x)；（4）Leaky ReLU : max(0.1x, x)；（5）Maxout；（6）ELU；    
1. *Sigmoid function* : when adopt Sigmoid as activation functions, it will bring three problems: first, Saturated neurons "kill" the gradients; Second, Sigmoid outputs are not zero-centered; Third, exp() is a bit compute expensive;       
2. *tanh* : Still kills gradients when saturated;   
3. *ReLU* : f(x) = max(0,x)； first, Does not saturate (in +region); second, Very computationally efficient; third, Converges much faster than sigmoid/tanh in practice. while, it still has these two cons, such as Not zero-centered output, and the gradient becomes zero when x<0.    
4. *Leaky ReLu* : it has four pros. first, Does not saturate; second, Computationally efficient; third, Converges much faster than sigmoid/tanh in practice! fourth, will not "die". it can derive "Parametric Rectifier (PReLU)", which represents as a form f(x) = max(alpha\*x,x), the para alpha can optimize by backprop algorithm. 
5. *Exponential Linear Units (ELU)* : thress pros. first, All benefits of ReLU; second, Does not die; third, Closer to zero mean outputs. while its comuptation requires exp(), which may bring expensive computation cost.    
6. *Maxout "Neuron"* : which represents as a form max(w1\*x+b1, w2\*x2+b2). it has three pros. one, Does not have the basic form of dot product -> nolinearity; two, Generalizes ReLU and Leaky ReLu; three, Linear Regime! Does not saturate! Does not die! However, it will meet the problem, which means doubles the number of parameters/neuron.   
- - -
Lecturer gives these tips for choosing activation function in practice.
> (1). Use ReLU, Be careful with your learning rates.    
> (2). Try out Leaky ReLU / Maxout / ELU.   
> (3). Try out tanh but don't expect much.   
> (4). Don't use sigmoid.   
#### 二. Data Preprocessing   
Step 1 : Preprocess the data   
original data -> zero-centered data (by using operator X -= np.mean(X, axis = 0)) -> normalized data(by using operator X /= np.std(X, axis = 0)). In practice, you may also see PCA and Whitening of the data --- the form as "original data" -> "decorrelated data" -> "whitened data".    
#### 三. Weight Initialization    
First idea : Small random numbers(gaussian with zero mean and 1e-2 standard deviation), such as w = 0.01\*np.random.randn(D,H). It works okay for small networks, but can lead to non-homogeneous distributions of activations across the layers of a network.    
Proper initialization is an active area of research....    
    
Batch Normalization   
1. compute the empirical mean and variance independently for each dimension.   
2. Normalize   
![](https://github.com/YunTuring/deeplearning.github.io/blob/master/CS231n-2016winter/Pictures/Batch%20Normalization.png)   
(1) improves gradient flow through the network.   
(2) Allows higher learning rates.   
(3) Reduces the strong dependence on initialization.    
(4) Acts as a form of regularization in a funny way, and sightly reduces the need for dropout,maybe.   










