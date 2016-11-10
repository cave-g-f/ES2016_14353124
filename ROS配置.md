##1、Installation
###1.1 configure your Ubuntu repositories
###1.2 Setup your source.list

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
###1.3 Set up your keys

```
sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
```
###1.4 Installation
First, make sure your Debian package index is up-to-date: 

```
sudo apt-get update
```
There are many different libraries and tools in ROS. I use Desktop-Full Install here.

```
sudo apt-get install ros-jade-desktop-full
```
![这里写图片描述](http://img.blog.csdn.net/20161110205241377)
###1.5 Initialize rosdep
Before you can use ROS, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS. 

```
sudo rosdep init
rosdep update
```
###1.6 Environment setup
It's convenient if the ROS environment variables are automatically added to your bash session every time a new shell is launched: 

```
echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
source ~/.bashrc
source /opt/ros/jade/setup.bash
```
###1.7 Getting rosinstall
rosinstall is a frequently used command-line tool in ROS that is distributed separately. It enables you to easily download many source trees for ROS packages with one command. 

```
sudo apt-get install python-rosinstall
```
![这里写图片描述](http://img.blog.csdn.net/20161110205300424)
##2 Tutorials
###2.1 Obtain source code of the installed packages

```
$ apt-get source ros-jade-laser-pipeline
```

