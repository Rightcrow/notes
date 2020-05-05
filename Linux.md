## Ubuntu



### Ubuntu mate



#### ssh

> 开启自启动

```
# 开机自动启动ssh命令
sudo systemctl enable ssh
 
# 关闭ssh开机自动启动命令
sudo systemctl disable ssh
 
# 单次开启ssh
sudo systemctl start ssh
 
# 单次关闭ssh
sudo systemctl stop ssh
 
# 设置好后重启系统
reboot
 
#查看ssh是否启动，看到Active: active (running)即表示成功
sudo systemctl status ssh
```

> 远程连接问题

<img src="C:\Users\zhang\AppData\Roaming\Typora\typora-user-images\image-20200427194024093.png" alt="image-20200427194024093" style="zoom:25%;" />



### ROS



#### ROS系统安装melodic

> Configure your Ubuntu repositories

```python
#Configure your Ubuntu repositories to allow "restricted," "universe," and "multiverse."
```

> Setup your sources.list

```shell
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

> Set up your keys

```shell
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
```

> 更新源地址

```shell
sudo apt-get update
```

> Installation

| Desktop-Full Install: (Recommended)** : ROS, [rqt](https://wiki.ros.org/rqt), [rviz](https://wiki.ros.org/rviz), robot-generic libraries, 2D/3D simulators and 2D/3D perception |
| ------------------------------------------------------------ |
| sudo apt install ros-melodic-desktop-full                    |
| **Desktop Install:** ROS, [rqt](https://wiki.ros.org/rqt), [rviz](https://wiki.ros.org/rviz), and robot-generic libraries |
| sudo apt install ros-melodic-desktop                         |
| **ROS-Base: (Bare Bones)** ROS package, build, and communication libraries. No GUI tools. |
| sudo apt install ros-melodic-ros-base                        |
| **Individual Package:** You can also install a specific ROS package (replace underscores with dashes of the package name): |
| sudo apt install ros-melodic-PACKAGE                         |

> ROS environment variables are automatically added to your bash session every time a new shell is launched:

```shell
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

> Dependencies for building packages

```shell
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
```

> Initialize rosdep

```shell
sudo apt install python-rosdep
sudo rosdep init
rosdep update
```

