# шпаргалка важных команды в ROS

создание пакете в ROS

```bash
catkin_create_pkg [pkg_name] [dep1 dep2 ...]
```

например

```bash
catkin_create_pkg study_pkg rospy roscpp
```

список всех пакетов, что видет ROS

```bash
rospack list
```

---

список всех запущенных нодов

```bash
rosnode list
```

инфа о конкретном ноде

```bash
rosnode info /NODE_NAME
```

список всех запущенных топиков

```bash
rostopic list
```

та же инфа но подробнее

```bash
rostopic list -v
```

инфа о конкретном топике

```bash
rostopic info /TOPIC_NAME
```

вывести данные, что публикуется в топик

```bash
rostopic echo /chatter
```

представить все ноды и топики графически

```bash
rqt_graph
```

---

все запущенные сервисы

```bash
rosservice list
```

инфа о конкретном сервисе

```bash
rosservice info /SERVICE_NAME
```

аргументы конкретного сервиса

```bash
rosservice args /SERVICE_NAME
```

---

список параметров в системе

```bash
rosparam list
```

получить значение параметра

```bash
rosparam get /PARAM_NAME
```

---

запустить rviz

```bash
rviz
```

---

сохранить карту, хранящуюся в map_server

```bash
rosrun map_server map_saver -f MY_SUPER_MAP_NAME
```

---

изменение параметров в реальном времени (не все параметры возможно менять)

```bash
rosrun rqt_reconfigure rqt_reconfigure
```

# настройка realsence

## установка SDK

[источник](https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md#installing-the-packages)

```bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE || sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE
```

```bash
sudo add-apt-repository "deb https://librealsense.intel.com/Debian/apt-repo $(lsb_release -cs) main" -u
```

```bash
sudo apt-get install librealsense2-dkms
```

```bash
sudo apt-get install librealsense2-utils
```

```bash
sudo apt-get install librealsense2-dev
```

```bash
sudo apt-get install librealsense2-dbg
```

## установка пакета

[источник](https://github.com/IntelRealSense/realsense-ros/tree/ros1-legacy)

```bash
cd ~/catkin_ws/src/
```

```bash
git clone https://github.com/IntelRealSense/realsense-ros.git
```

```bash
cd realsense-ros/
```

```bash
git checkout `git tag | sort -V | grep -P "^2.\d+\.\d+" | tail -1`
```

# настройка YDLidar

## установка SDK

```bash
cd ~
```

```bash
wget https://www.ydlidar.com/dowfile.html\?cid\=6\&type\=4
```

```bash
unzip dowfile.html\?cid=6\&type=4
```

```bash
mv YDLidar-SDK-master YDLidar-SDK
```

```bash
cd YDLidar-SDK/build
```

```bash
cmake ..
```

```bash
make
```

```bash
sudo make install
```

## установка пакета

```bash
cd ~/catkin_ws/src/
```

```bash
git clone https://github.com/YDLIDAR/ydlidar_ros_driver.git
```

```bash
chmod 0777 ydlidar_ros_driver/startup/*
```

```bash
sudo sh ydlidar_ros_driver/startup/initenv.sh
```