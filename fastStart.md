# подготовка к установке

* [по этому видосу выделяем на бубунту 100 гигов (100000 мб, смотрим внимательно единицы измерения) жесткого диска ](https://www.youtube.com/watch?v=OkTkbo54Ggs)

* [по ссылке скачивает файл образа диска для установки ubuntu 20.04](https://releases.ubuntu.com/focal/)

* [по этой ссылке качаем прогу которая сделает из обычно флешки загрузочную](https://ultraiso.su/)

# установка

* втыкаем флешку в комп и перезагружаем, обычно сразу появляется окошко, в котором выбираем установку бубунты (если нет, то в bios ставим флешку на первое место в менеджере загрузок)

* важное замечание - при установке ubuntu вам будет предложено подключиться на wi-fi - этот пункт надо скипнуть; также предложат установить проприетарные драйверы, нужно убедиться что не стоит галочка, они нам не нужны. после установки выполнить команду `sudo apt update && sudo apt upgrade`, это подгрузит все недостающие репозитории. если что смотрим видос `https://www.youtube.com/watch?v=e2uv6TKzxmk&t=327s`

# [!!! если слетел загрузчик винды по этому видосу его восстанавливает](https://www.youtube.com/watch?v=KWsFAyluJ0U&list=LL&index=7)

# установка русского языка (если он не установился)

```bash
cd ~
```

```bash
sudo apt-get install language-pack-ru
```

```bash
sudo apt-get install language-pack-gnome-ru
```

```bash
sudo apt-get install language-pack-kde-ru
```

```bash
sudo update-locale LANG=ru_RU.UTF-8
```

* перезагружаем кампуктер

# установка драйверов для карт NVIDIA

```bash
sudo apt install nvidia-driver-515 nvidia-dkms-515
```

* далее перезагружаем комп и при запуске соглашаемся с переименованием папок и проверяем, что драйвер запустился командой `nvidia-smi`

# установка git

```bash
cd ~
```

```bash
sudo apt install apt-transport-https
```

```bash
sudo apt install git
```

```bash
sudo apt update && sudo apt upgrade
```

# установка ohmyzsh

```bash
cd ~
```

```bash
sudo apt install curl
```
```bash
sudo apt install zsh
```

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

```bash
git clone https://github.com/powerline/fonts.git
```

```bash
cd fonts
```

```bash
./install.sh
```

```bash
cd ..
```

```bash
rm -r fonts
```

```bash
sudo apt update && sudo apt upgrade
```

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

## установка нужных пакетов для ROS

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
cd ~
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
cd ..
```

```bash
echo "source ~/catkin_ws/devel/setup.zsh" >> ~/.zshrc
```

```bash
sudo apt update && sudo apt upgrade
```

# установка nautilus (открывать папки и файлы как админ)

```bash
sudo apt install -y nautilus-admin
```

```bash
nautilus -q
```

```bash
sudo apt update && sudo apt upgrade
```

# установка ssh

```bash
sudo apt-get install ssh
```

```bash
sudo apt install openssh-server
```

```bash
sudo apt install net-tools
```

```bash
sudo apt update && sudo apt upgrade
```

# расширенные настройки системы

```bash
sudo apt-get install gnome-tweaks
```

# установка speedtest

```bash
sudo apt-get install python3-pip
```

```bash
sudo pip install speedtest-cli
```

```bash
speedtest
```

```bash
sudo apt update && sudo apt upgrade
```

# установка cmatrix

```bash
sudo apt install cmatrix
```

```bash
cmatrix
```

```bash
sudo apt update && sudo apt upgrade
```

# делу час - потехе время!

```bash
sudo apt install steam
```

```bash
sudo apt update && sudo apt upgrade
```

# терминальный мультиплексор tmux

```bash
sudo apt install tmux
```

* создаем конфиг-файл

```bash
touch ~/.tmux.conf
```

* назначаем комбинацию CTRL + q как командную

```bash
echo "set-option -g prefix C-q" >> ~/.tmux.conf
```

* делаем возможным масштабировать терминалы мышкой

```bash
echo "set -g mouse on" >> ~/.tmux.conf
```

# работа с dualshock4 и другими геймпадами

[драйвер ds4drv](https://github.com/chrippa/ds4drv)

```bash
sudo pip install ds4drv
```

[установка jstest-gtk (прога для проверки/настройки)](https://onstartup.ru/utility/jstest-gtk/)

```bash
sudo apt install jstest-gtk
```

# работа с C#

[установка SDK](https://learn.microsoft.com/ru-ru/dotnet/core/install/linux-ubuntu#2004)

# вывод структуры папок в консоль

```bash
sudo apt install tree
```

# управление процессами

```bash
sudo apt install htop
```

# запись видео фрагмента экрана

```bash
sudo apt install peek
```

# проигрывание видео

```bash
sudo apt install totem
```

# libreOffice

```bash
sudo apt install libreoffice-gnome libreoffice
```

## установка TNR

```bash
sudo apt-get install ttf-mscorefonts-installer
```

## русский язык и орфография

```bash
sudo apt-get install libreoffice-l10n-ru libreoffice-help-ru
```

```bash
sudo apt-get install hunspell-ru
```

## вебкамера

```bash
sudo apt install cheese
```

# отсюда рекомендуется качать телегу

[ссылка на сайт](https://desktop.telegram.org/?setln=ru)

# отсюда рекомендуется качать VS Code

[ссылка на сайт - выбираем .deb](https://code.visualstudio.com/download)

# тут можно качнуть GUI-версию github-desktop
[ссылка на реп - выбираем .deb](https://github.com/shiftkey/desktop/releases)

# тут можно качнуть discord
[ссылка на сайт - выбираем .deb](https://discord.com/download)

# расширения

## включение жестов

```bash
sudo add-apt-repository ppa:touchegg/stable
```

```bash
sudo apt install touchegg
```

```bash
systemctl status touchegg.service && systemctl start touchegg.service
```

# расширения

## Burn My Windows

<p align="center">
<img src="screenshots/burnMyWindows/1.png" width="600">
</p>

## Clipboard Indicator

<p align="center">
<img src="screenshots/clipboardIndicator/1.png" width="600">
</p>

## Net speed Simplified

<p align="center">
<img src="screenshots/netSpeedSimplified/1.png" width="600">
</p>

## OpenWeather

<p align="center">
<img src="screenshots/openWeather/1.png" width="600">
</p>

<p align="center">
<img src="screenshots/openWeather/2.png" width="600">
</p>

`Saint-P`  
`59.950185, 30.317480`  

<p align="center">
<img src="screenshots/openWeather/3.png" width="600">
</p>

<p align="center">
<img src="screenshots/openWeather/4.png" width="600">
</p>

<p align="center">
<img src="screenshots/openWeather/5.png" width="600">
</p>

<p align="center">
<img src="screenshots/openWeather/6.png" width="600">
</p>

## Public IP

<p align="center">
<img src="screenshots/publicIP/1.png" width="600">
</p>

## Shell Configurator

<p align="center">
<img src="screenshots/shellConfig/1.png" width="600">
</p>

<p align="center">
<img src="screenshots/shellConfig/2.png" width="600">
</p>

<p align="center">
<img src="screenshots/shellConfig/3.png" width="600">
</p>

## Vitals

<p align="center">
<img src="screenshots/vitais/1.png" width="600">
</p>

## WinTile

<p align="center">
<img src="screenshots/winTile/1.png" width="600">
</p>

## X11 Gestures

<p align="center">
<img src="screenshots/X11/1.png" width="600">
</p>

## Dash to Dock

<p align="center">
<img src="screenshots/dashToDock/1.png" width="600">
</p>

<p align="center">
<img src="screenshots/dashToDock/2.png" width="600">
</p>

* после этого удаляем расширение т.к. оно глючное и перезапускаем комп, у нас остается только красота

# включение гибернации в linux

[проверить размер swap-файла (если он меньше оперативы - надо делать размером с нее)](https://andreyex.ru/ubuntu/kak-uvelichit-razmer-swap-v-ubuntu/)

[ссылка на статью](https://www.linuxuprising.com/2021/08/how-to-enable-hibernation-on-ubuntu.html)
