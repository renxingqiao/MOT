# MOT
基于时序预测和多模态融合的自动驾驶3D多目标追踪算法研究

这里简单介绍部分工作内容

## 概述

针对传统3D多目标跟踪算法无法充分利用历史状态信息的问题，提出了一种基于时间序列预测的3D多目标跟踪算法，通过内部记忆与外部记忆两个模块实现对目标运动状态建模，并由门控循环单元进行状态更新。

研究了一种融合激光雷达和视觉的数据关联算法，以解决复杂交通场景下因遮挡而导致目标跟踪丢失的问题。

## 传感器融合

相机标定，解决相机畸变问题。

相机与激光雷达外参标定

![image](https://user-images.githubusercontent.com/88017321/223400093-d456c696-ce11-4b6a-ac9c-6c11bc1d0994.png)
