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

# настройка YDLidar