[TOC]



# Apolo 

### 高精度地图与自动驾驶的关系?

自动驾驶的5个级别:

L2及以下不需要高精度地图, L3-L4级别

### 什么是高精度地图?

![image-20190602142405500](/Users/hehui/Documents/HNotes/Notes/assets/image-20190602142405500.png)

实时性.

### 与传统地图的联系?

传统导航地图: 有向图结构, 方向性的引导,  行人, 决策等都由人来完成.

高精地图:  如何让车辆更好的理解环境. 车道线, 左右转向

## 高精地图- 无人驾驶模块的核心

![image-20190602143609220](/Users/hehui/Documents/HNotes/Notes/assets/image-20190602143609220.png)

HMI: Human-Machine Interface 人机交互的接口

#### 高精与定位:

![image-20190602144028566](/Users/hehui/Documents/HNotes/Notes/assets/image-20190602144028566.png)

GNSS: *Global Navigation Satellite System* (*GNSS*) receivers, using the GPS, GLONASS, Galileo or BeiDou system减少搜索范围.

定位:  粒子滤波,  看到左边有一颗树(Feature)

可以提供的Feature: 电线杆, 车道线,停止线,人行横道. 能提供很多的约束.

#### 高精与感知:

Lidar: 

Camera: 夜间

radar: 穿透力强, 精度低. 雾霾,阴雨天.

根据以上传感器的局限性, 高精地图可视作离线的传感器(静态的perception), 高精地图上标注了所有的道路元素的位置.

在深度学习中,仅依靠传感器会有误识别, 高精地图能给出一个很好的先验, 以提高识别率.

其他case: 车流线密集的路口, 很难感知到前方的红绿灯, 此时的高精度地图可以给出规划预测决策.

#### 高精与规划,预测,决策模块:

规划: 全局(长距离)与局部(短距离)规划

预测: 道路参与者可能的行驶轨迹.

决策: 根据规划和预测的结果, 进行决策.

控制: 

障碍物: 

#### 高精与仿真:

#### 高精地图的挑战: 

特殊的路网, 交通场景:  比如重庆

雪天: 



## 高精地图的采集和生产: 

### ![image-20190602152234058](/Users/hehui/Documents/HNotes/Notes/assets/image-20190602152234058.png)

`GPS: ` 空间坐标(x,y,z) 三个变量-> 需要三个方程

​	第四颗卫星: 误差

​	评价: 在空旷的环境如高速, 信号好,定位精度好.  在城镇市区, 由于多径效应会有偏移. 精度会下降到

`IMU:` 三轴加速度和三轴陀螺仪. 存在累计漂移

`轮速计: (轮式里程计): `

`Lidar:`

![image-20190602153347774](/Users/hehui/Documents/HNotes/Notes/assets/image-20190602153347774.png)





### 计算模型:

![image-20190602153542579](/Users/hehui/Documents/HNotes/Notes/assets/image-20190602153542579.png)

#### 简化的模型:

![image-20190602153750080](/Users/hehui/Documents/HNotes/Notes/assets/image-20190602153750080.png)

求一个预测位置和实际位置的一个最小化.

融合 + SLAM算法校正pose, 实现空间结构的三维重建

### 一些方案:

百度: Camera+Lidar

Nvdia: 

宽凳??
DeepMotion: 号称cm级

![image-20190602160940955](http://ww1.sinaimg.cn/large/006tNc79gy1g3mvlzz5mjj31580giayl.jpg)



## 高精地图的格式:

NDS:

POI: 兴趣点

![image-20190602161913552](http://ww4.sinaimg.cn/large/006tNc79gy1g3mvvvk3x1j313y0g6asf.jpg)

OpenDrive:

![image-20190602171733379](http://ww1.sinaimg.cn/large/006tNc79gy1g3mxkkvvekj30z20gstjr.jpg)

<img src='http://ww1.sinaimg.cn/large/006tNc79gy1g3mvwk21wrj31040jm15e.jpg' width=500 align='left'>



![image-20190602162822974](http://ww2.sinaimg.cn/large/006tNc79gy1g3mw5ewyq4j30zy0je7gs.jpg)





## 业界的高精地图:

* HERE
* MobileEye
* Waymo
* TomTom

### HERE: 

地图做成一个基于云端的地图, 更新快.

Live Map: 

![image-20190603095042194](http://ww4.sinaimg.cn/large/006tNc79gy1g3nq9ziuzpj31820l0b29.jpg)



![image-20190603112729723](http://ww3.sinaimg.cn/large/006tNc79gy1g3nt2n0ssuj31bw0ms4mw.jpg)

#### Map-Learning:

![image-20190603112921383](http://ww4.sinaimg.cn/large/006tNc79gy1g3nt4l2hp1j31c80nunpd.jpg)

点云分割, 点云场景的物体识别.

#### HERE HD Live Map-product:

![image-20190603113437207](http://ww4.sinaimg.cn/large/006tNc79gy1g3nta2agogj31bw0mqhdt.jpg)





### MobileEye:

![image-20190603114411969](http://ww2.sinaimg.cn/large/006tNc79gy1g3ntk19xgmj31840nqh5g.jpg)

#### MobileEye-Pillars of Autonomous Driving:

![image-20190603114537197](http://ww4.sinaimg.cn/large/006tNc79gy1g3ntli62msj31bw0nmnpd.jpg)

利用强化学习来训练驾驶策略.



#### MobileEye-Map as back-up sensors:

![image-20190603114926649](http://ww3.sinaimg.cn/large/006tNc79gy1g3ntphhzpmj31dk0l0hdt.jpg)

虚拟lane: 



####  MobileEye-RoadBook:

![image-20190603115359917](http://ww4.sinaimg.cn/large/006tNc79gy1g3ntu8bh5rj31dm0mgu0x.jpg)

Road Segment Data:



### Google Waymo:

![image-20190603120535849](http://ww2.sinaimg.cn/large/006tNc79gy1g3nu6ay917j31bq0lwnpd.jpg)



![image-20190603120837250](http://ww3.sinaimg.cn/large/006tNc79gy1g3nu9fj5cbj31700k4nkv.jpg)



### TomTom:





## ROS:

#### ROS特征：

* 点对点：  Node 之间的消息通信
* 分布式： 多机之间的
* 跨语言： 只需按ROS提供的接口，完成消息的订阅和分发。
* 轻量级程序： 用户只需要关心自己核心模块的一个算法逻辑。
* 开源社区： 贡献自己的代码

#### ROS WorkSpace Env：

* 

