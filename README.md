# LVI-SAM

Modifiled for ROS2GO system
---

## Dependency


- [gtsam-4.0.3]
```
  git clone -b 4.0.3 https://github.com/borglab/gtsam.git
  cd gtsam
  mkdir build & cd build
  cmake ..
  sudo make install
```

## Compile

You can use the following commands to download and compile the package.

```
cd ~/catkin_ws/src
git clone https://github.com/geekhub330/LVI-SAM-ROS2GO
cd ..
catkin_make
```

---

## Datasets

<p align='center'>
    <img src="./doc/sensor.jpeg" alt="drawing" width="600"/>
</p>

The datasets used in the paper can be downloaded from Google Drive. The data-gathering sensor suite includes: Velodyne VLP-16 lidar, FLIR BFS-U3-04S2M-CS camera, MicroStrain 3DM-GX5-25 IMU, and Reach RS+ GPS.

```
https://drive.google.com/drive/folders/1q2NZnsgNmezFemoxhHnrDnp1JV_bqrgV?usp=sharing
```

**Note** that the images in the provided bag files are in compressed format. So a decompression command is added at the last line of ```launch/module_sam.launch```. If your own bag records the raw image data, please comment this line out.

<p align='center'>
    <img src="./doc/jackal-earth.png" alt="drawing" width="286.5"/>
    <img src="./doc/handheld-earth.png" alt="drawing" width="328"/>
</p>

**New:** more datasets are available at [LVI-SAM-Easyused](https://github.com/Cc19245/LVI-SAM-Easyused).

---

## Run the package

1. Configure parameters:

```
Configure sensor parameters in the .yaml files in the ```config``` folder.
```

2. Run the launch file:
```
roslaunch lvi_sam run.launch
```

3. Play existing bag files:
```
rosbag play handheld.bag 
```








