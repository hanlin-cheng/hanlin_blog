---
title: 安装VINS-Fusion
date:
tags: 
- VINS
categories:
- slam_config
description:
top_img: false

---

# 安装VINS-Fusion 

## **Part1:** 

```shell
mkdir -p ~/vin-fusion_ws/src   
cd ~/vin-fusion_ws/src 
git clone https://github.com/HKUST-Aerial-Robotics/VINS-Fusion.git 
cd ../ 
catkin_make 
source ~/catkin_ws/devel/setup.bash 
```

 