# task 1,2_AI_smart-methods
* task1:install ROS Neotic on Ubuntu 20.04 
* task2: Ros install algorithm on Jetson nano

# task1: install ROS Neotic on Ubuntu

1.  download VirtualBox.
2.  download [Ubuntu 20.04.4](https://releases.ubuntu.com/20.04.4/?_ga=2.254970826.372918294.1658034976-1795708661.1658034976).
3. create the virttual machine.

## install ROS Noetic

**Setup your sources.list**

Setup your computer to accept software from packages.ros.org.

``` sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'```

**Set up your keys**

```
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

**Installation**

First, make sure your Debian package index is up-to-date

`sudo apt update`

**Desktop-Full Install: (Recommended) :**: Everything in Desktop plus 2D/3D simulators and 2D/3D perception packages

**sudo apt install ros-noetic-desktop-full**

`sudo apt install ros-noetic-desktop-full`

**Environment setup**
```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
 ```
 **Dependencies for building packages**
 
 `sudo apt install python3-rosdep python3-rosinstall python3-rosinstall
-generator python3-wstool build-essential`

**Initialize rosdep**
```
 sudo apt install python3-rosdep
 sudo rosdep init
 rosdep update
```

**start the ROS**

`roscore`


 # task2: Ros install algorithm on Jetson nano
 
 1. download Xubuntu 20.4
 2. download balena
 
 ## install ROS2 Foxy
 
 **Set locale**
 ```
locale  # check for UTF-8
sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8
locale  # verify settings
```
 
**Setup Sources**

You will need to add the ROS 2 apt repositories to your system. First, make sure that the Ubuntu Universe repository is enabled by checking the output of this command.

`apt-cache policy | grep universe`

This should output a line like the one below:
```
500 http://us.archive.ubuntu.com/ubuntu focal/universe amd64 Packages
    release v=20.04,o=Ubuntu,a=focal,n=focal,l=Ubuntu,c=universe,b=amd64
```
If you don’t see an output line like the one above, then enable the Universe repository with these instructions.
```
sudo apt install software-properties-common
sudo add-apt-repository universe
```

Now add the ROS 2 apt repository to your system.
```
sudo apt update && sudo apt install curl gnupg2 lsb-release
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key  -o /usr/share/keyrings/ros-archive-keyring.gpg
```

Then add the repository to your sources list.
```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```
 
## Install ROS 2 packages
Update your apt repository caches after setting up the repositories.
`sudo apt update`

ROS 2 packages are built on frequently updated Ubuntu systems. It is always recommended that you ensure your system is up to date before installing new packages.

`sudo apt upgrade`

Desktop Install (Recommended): ROS, RViz, demos, tutorials.

`sudo apt install ros-foxy-desktop`

## Environment setup

Set up your environment by sourcing the following file.

`source /opt/ros/foxy/setup.bash`








