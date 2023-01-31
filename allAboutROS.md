# установка ROS

```bash
cd ~
```

```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

```bash
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

```bash
sudo apt update && sudo apt upgrade
```

```bash
sudo apt install ros-noetic-desktop-full
```

```bash
echo "source /opt/ros/noetic/setup.zsh" >> ~/.zshrc
```

```bash
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```

```bash
sudo apt install python3-rosdep
```

```bash
sudo rosdep init
```

```bash
rosdep update
```

```bash
sudo apt install python-is-python3
```

```bash
sudo apt update && sudo apt upgrade
```

# установка нужных пакетов для ROS

```bash
cd ~
```

```bash
sudo apt install ros-noetic-dwa-local-planner
```

```bash
sudo apt install ros-noetic-move-base
```

```bash
sudo apt install ros-noetic-amcl
```

```bash
sudo apt install ros-noetic-gmapping
```

```bash
sudo apt-get install ros-noetic-map-server
```

```bash
sudo apt-get install ros-noetic-ros-control ros-noetic-ros-controllers
```

```bash
sudo apt-get install ros-noetic-joy
```

```bash
sudo apt-get install libspnav-dev
```

```bash
sudo apt update && sudo apt upgrade
```

## установка turtle-bot (пакеты для catkin_ws)

```bash
cd
```

```bash
mkdir -p ~/catkin_ws/src
```

```bash
cd catkin_ws/src
```

```bash
git clone https://github.com/ROBOTIS-GIT/turtlebot3.git -b noetic-devel
```

```bash
git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git -b noetic-devel
```

```bash
git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git -b noetic-devel
```

```bash
cd ~/catkin_ws
```

```bash
catkin_make
```

```bash
cd
```

```bash
echo "source ~/catkin_ws/devel/setup.zsh" >> ~/.zshrc
```

```bash
sudo apt update && sudo apt upgrade
```

# шпаргалка важных команды в ROS

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
