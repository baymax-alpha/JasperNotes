# torch.tutorial

---



1. `import torch` what happend?

2. `Torch.cuda.is_available()` what be called? 

   python source:

   ```python
   __init__.py
   def is_available()
   	return torch._C._cuda_getDeviceCount()>0
   ```

   ​	所以, 是调用了_C.cpython-35m-x86_64-linux-gnu.so c++的共享库.

3. torch.Tensor  调用了什么?

   tensor.py 的类

4. 自动求导机制: torch 如何实现的? 

5. models

   resnet.named_parameters / resnet.named_parameters()

   Renet.named_modules/ 

   Modules/ submodules

   









Cambricon Torch







### 一些概念：

动态神经元： 

ReLU： 激活函数

反向传播更新参数（权重）

Gradient descent 梯度下降：

 Cost Fucntion： $Cost = (Predicted - real)^2 = (wx-y)^2$

$W = \left [w_{00}, w_{01} …    \right]$

#### 2.神经网络黑盒：

feature_represention: 

迁移学习

数据 + 搭建计算图

拟合， 分类

#### 3.安装

Tensor and Dynamic neural networks.

Variable : 参数。



什么是激励函数？

非线形手段：relu， sigmoid,  tanh, softmax