
### Overview
#### 1. One time setup   
*activation functions, preprocessing, weight initialization, regularization, gradient checking*
#### 2. Training dynamics   
*babysitting the learning process, parameter updates, hyperparameter optimization*
#### 3. Evaluation   
*model ensembles*    

#### Activation functions: 激活函数的作用增加非线性，这样深层神经网络才可以提取更多不同的特征。   
（1） Sigmoid；（2）tanh；（3）ReLU : max(0,x)；（4）Leaky ReLU : max(0.1x, x)；（5）Maxout；（6）ELU；    
1. Sigmoid function : when adopt Sigmoid as activation functions, it will bring three problems: first, Saturated neurons "kill" the gradients; Second, Sigmoid outputs are not zero-centered; Third, exp() is a bit compute expensive;       
2. tanh : Still kills gradients when saturated;   
3. ReLU : f(x) = max(0,x)； first, Does not saturate (in +region); second, Very computationally efficient; third, Converges much faster than sigmoid/tanh in practice. while, it still has these two cons, such as Not zero-centered output, and the gradient becomes zero when x<0.   





