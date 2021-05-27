# AlexeyAB版YOLOv3环境配置

2021.5.27已拷贝至个人仓库

https://github.com/layman-hu/darknet



CUDA10.0

CUDNN7.5.0

Python3.7.1

conda create -n darknet python=3.7

![img](https://cdn.nlark.com/yuque/0/2021/png/12462708/1621484248340-8876cdaf-33d5-483b-bbbd-7773b1b57d35.png)



#### 1.props文件

C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\extras\visual_studio_integration\MSBuildExtensions目录里面CUDA的四个文件

![img](https://cdn.nlark.com/yuque/0/2021/png/12462708/1621491452374-699dbd05-1452-47fa-ae49-41bebd9277ad.png)

复制到

C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\MSBuild\Microsoft\VC\v150\BuildCustomizations



#### 2.修改cu文件

import os

os.chdir("../darknet/src")

!sed -i 's/, cudaStreamCaptureModeGlobal//' network_kernels.cu

!cat network_kernels.cu



#### 3.opencv的dll文件

..\opencv\opencv\build\x64\vc14\bin目录的三个dll文件

（文件已传至蓝奏云https://4399play.lanzoui.com/b0a9w4pwd 密码:1krq）

![img](https://cdn.nlark.com/yuque/0/2021/png/12462708/1621493809635-1cdc370f-3957-4cc0-8510-574692fd5010.png)

复制到

..\darknet\build\darknet\x64目录

![img](https://cdn.nlark.com/yuque/0/2021/png/12462708/1621493835193-6fce089e-9e98-432b-bba7-190dc0b083df.png)



#### 4.vs配置

选择当前电脑系统版本，VS选2017平台工具集

![img](https://cdn.nlark.com/yuque/0/2021/png/12462708/1621491564186-4d741001-dbc6-4b21-b846-476b987707bc.png)

电脑的GPU型号为MX250，算力3.5，所以对应CUDA的算力为35

![img](https://cdn.nlark.com/yuque/0/2021/png/12462708/1621491582091-4e23bf79-e645-4597-a770-abef70bbaf1e.png)



最后build即可