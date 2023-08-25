---
title: LIO-SAM运行
date:
tags: 
- LIO-SAM
categories:
- command
description:
top_img: false

---

# LIO-SAM运行

## part1：数据集运行

### 1.环境变量

```shell
source devel/setup.bash
```

### 2.启动lio-sam功能包

```shell
roslaunch lio_sam run.launch
```

### 3.播放数据集

```shell
rosbag play outdoor.bag
```



## part2：实测运行

### 1.打开config文件夹下的参数文件params，修改imu和点云话题

![10 sam:  \# Topics  pointCloudTopic: "/points raw"  \# pointCloudTopic: "/velodyne_points"  imuTopic: "/imu/data"  \# imuTopic: "imu correct"  \# imuTopic: "imu raw"  odomTopic: "odometry/imu"  gpsTopic: "odometry/gpsz"  \# Point cloud data  \# IMIJ data  \# IMIJ pre-preintegration odometry, same frequency as IMIJ  \# GPS odometry topic from navsat, see module navsat.launch file ](media/e26b16e4dfa08f27a6be90000c53f58e.png)



### 2.修改imu矫正参数

![\#IMU Settings  imuAccNoise: 1.9740799873834897e-02  imuGyrNoise: 2,3704854385698929+03  imuAccBiasN: 4.3015781912824339+04  imuGyrBiasN: 2.6685224155471368+05  imuGravity: 9.80511  imuRPYWeight: 0.01  imuAccNoise: 3,9939570888238808+03  imuGyrNoise: 1.5636343949698187e-03  imuAccBiasN: 6,4356659353532566+05  imuGyrBiasN: 3.5640318696367613e-05  imuGravity: 9.80511  imuRPYWeight: 0.01 ](media/d46f4d8198bf146ef7995d5708b2b454.png)



### 3.修改激光雷达到imu标定参数

![[png]](media/dbebbbdaf4c6e4278a0ac2e62db89a81.png)



### 4.添加环境变量

```shell
source devel/setup.bash
```



### 5.启动xsens

```shell
sudo chmod 777 /dev/ttyUSB\*
roslaunch xsens_mti_driver xsens_mti_node.launch
```



### 6.启动激光雷达

```shell
roslaunch velodyne_pointcloud velodyne_vlp16.launch
```



### 7.启动LIO-SAM

```shell
roslaunch lio_sam run.launch
```


