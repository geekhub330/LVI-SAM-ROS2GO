# LVI-SAM

Modifiled for ROS2GO system
---

## Dependency


- [gtsam-4.0.3]
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
git clone https://github.com/TixiaoShan/LVI-SAM.git
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

---

## Related Packages

  - [LVI_SAM_fixed by epicjung](https://github.com/epicjung/LVI_SAM_fixed)
  - [LVI-SAM-modified by skyrim835](https://github.com/skyrim835/LVI-SAM-modified)
  - [LVI-SAM-Easyused by Cc19245](https://github.com/Cc19245/LVI-SAM-Easyused)

---

## TODO

  - [ ] Update graph optimization using all three factors in imuPreintegration.cpp, simplify mapOptimization.cpp, increase system stability 

---

## Paper 

Thank you for citing our [paper](./doc/paper.pdf) if you use any of this code or datasets.

```
@inproceedings{lvisam2021shan,
  title={LVI-SAM: Tightly-coupled Lidar-Visual-Inertial Odometry via Smoothing and Mapping},
  author={Shan, Tixiao and Englot, Brendan and Ratti, Carlo and Rus Daniela},
  booktitle={IEEE International Conference on Robotics and Automation (ICRA)},
  pages={5692-5698},
  year={2021},
  organization={IEEE}
}
```

---

## Acknowledgement

  - The visual-inertial odometry module is adapted from [Vins-Mono](https://github.com/HKUST-Aerial-Robotics/VINS-Mono).
  - The lidar-inertial odometry module is adapted from [LIO-SAM](https://github.com/TixiaoShan/LIO-SAM/tree/a246c960e3fca52b989abf888c8cf1fae25b7c25).
