# Pytorch_Source

---



1. pytorch 中的tensor 数据类

   1. raw_mutable_data 是什么 

      actually allocate memory: <TensorImpl:740> 

      ```cpp
      storage_.data()==nullptr
      storage_.device_type()
      storage_.set_data_ptr(allocator->allocate())
      
      ```

      

2. 提供了哪些通用函数. 

3. 

4. 架构: 几个模块分别做了什么

5. 一些机制

   pytorch 中 python 与 c++





```cpp
TensorImpl:
|-stroge
|-size
|-
```









### MLU适配



```cpp
/*类型转换*/
Scalar nms_thres
float nms_thres_f = nms_thres.to<float>();
```

创建MLU Tensor

```cpp
auto* bbox=at::empty({}, bboxes.options())
auto* bbox_impl = bbox_unsafeGetTensorImpl();
auto bbox_cnml = bbox_impl->CreateCnmlTensor(CNML_TENSOR, MLUTypeMetaToMluDataType(bbox.dtype()))
```



## MLU 与 CPU 界面



1. ### Tensor

   #### 内存的拷入拷出  

   什么时候从cpu拷入mlu, 什么时候从mlu拷出cpu??

​       维度什么时候会变??

2. ### MLU的数据类型





## setuptools 学习&&CppExtension

1.demo

>
>
>1>.包含所编译的文件,
>
>2>.生成包的结构
>
>>源文件,依赖,如何让调用者找到该包. Import demo 发生了什么.
>>
>>编译包: python setup.py bdist_egg
>>
>>安装包: python setup.py install
>>
>>查看包: file/tree
>
>3>. Feature:
>
>
>
>Entry_point

```python
tree:
setuptools.pie
  |-setup.py
  |-src:
    |- __init__.py
  
  
 setup.py: 
  
  from setuptools import setup, find_packages 
	setup(
  name=,
  version=,
  packages=find_packages("src"),
  package_dir = {}
  package_data = {}
  
  )
 
```







## Python 与 C++交互

1. import noody 发生了什么?

   >1. python的环境变量 sys.path 找: 安装的包在site-packages 下
   >
   >   egg 包的结构:
   >
   >2. Noddy3.py文件
   >
   >   ```python
   >   def __bootstrap__():
   >     global __bootstrap__, __loader__, __file__
   >     import sys, pkg_resources, imp
   >     __file__ = pkg_resources.resource_filename(__name__, "noddy3module.cpython-35m-x86_64-linux-gnu.so")
   >     __loader__ = None;
   >     del __bootstrap__, __loader__
   >     imp.load_dynamic(__name__, __file__)
   >   __bootstrap__()
   >   ```
   >
   >   
   >
   >







1. python 框架的整体了解

   >1. python 与 cpp的交互, cpp_extension,  
   >
   >2. pytorch
   >
   >   >* jit 融合
   >   >* 逐层机制
   >   >* Tensor 
   >
   >3. 熟悉新的开源方案
   >
   >4. 调试代码技巧: dump 数据技巧

2. cambricon的一些机制

   >离线模型
   >
   >算子注册机制
   >
   >网络加速机制: 量化

3. 熟悉4+3网络: 

4.  熟悉编译器, 一些工具的使用.