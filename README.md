# MOT
基于时序预测和多模态融合的自动驾驶3D多目标追踪算法研究

这里简单介绍部分工作内容

## 概述

针对传统3D多目标跟踪算法无法充分利用历史状态信息的问题，提出了一种基于时间序列预测的3D多目标跟踪算法，通过内部记忆与外部记忆两个模块实现对目标运动状态建模，并由门控循环单元进行状态更新。

研究了一种融合激光雷达和视觉的数据关联算法，以解决复杂交通场景下因遮挡而导致目标跟踪丢失的问题。

## 传感器融合

相机标定，解决相机畸变问题。

多激光雷达外参标定 利用多颗激光雷达解决点云稀疏问题

![image](https://user-images.githubusercontent.com/88017321/223401168-f0776892-41ed-4ff0-b15b-d722d149f1aa.png)


时间同步

![image](https://user-images.githubusercontent.com/88017321/223400923-434aafa3-194c-4e8c-af0f-1b48302e7f31.png)


相机与激光雷达外参标定

![image](https://user-images.githubusercontent.com/88017321/223400352-c1c95c8c-6cc1-4e9d-8a43-4275dee5e8ec.png)

![image](https://user-images.githubusercontent.com/88017321/223400397-b1f967c2-409a-42e9-990c-2ba130ae9977.png)

## 基于时序预测的3D多目标跟踪算法框架

基于循环神经网络，以多帧运动状态及隐状态为输入，输出预测状态及新的隐状态。其余组件暂时采用AB3D基线方法。

![image](https://user-images.githubusercontent.com/88017321/223402129-ce08a562-bec6-44be-a56e-05533f8ed402.png)

检测器采用PV-RCNN

![image](https://user-images.githubusercontent.com/88017321/223402447-5eca0eb0-3032-45a0-8e98-00e46a751b1b.png)


![image](https://user-images.githubusercontent.com/88017321/223402409-9e4317df-41b0-4fdc-a922-c4557443c5c0.png)

## 基于循环自回归的运动状态预测网络结构

核心组件为GRU

![image](https://user-images.githubusercontent.com/88017321/223402567-cdde089e-fa4e-4a82-8771-94e0b5e3f42c.png)

关联部分采用3D Iou + 匈牙利算法

![image](https://user-images.githubusercontent.com/88017321/223402992-b62316f8-1dfc-4097-8902-9c6eb5fa7ec2.png)

## 基于多模态融合的数据关联算法

STP-ReID网络框架

![image](https://user-images.githubusercontent.com/88017321/223404211-dfa711ac-f46a-4460-9d09-c1ef7cc7d7ad.png)

辅助信息特征嵌入

![image](https://user-images.githubusercontent.com/88017321/223404274-1d475036-1fc0-460d-9463-368cf3d3d476.png)

## 可视化

![image](https://user-images.githubusercontent.com/88017321/223404500-a3a8dbbe-43f4-4e73-97ac-907248782e0d.png)

![image](https://user-images.githubusercontent.com/88017321/223404516-87a7c795-5828-4501-bdc5-a877f1c07d63.png)
