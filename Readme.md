#ros_google_sbi

ros_google_sbi contains a Google search by image (sbi) interface written in Python for ROS. It uses py_google_sbi.

The ROS Package may be build and installed using catkin.

##install

Non ROS server dependencies python + modules: curl nltk (used for stopword filter)

Non ROS client dependencies python + modules: opencv (snapshot) matplotlib (draws pie-charts)

install ROS, catkin, create a catkin workspace see http://wiki.ros.org/catkin/Tutorials/create_a_workspace

```
cd <catkin_ws>/src

git clone --recursive https://github.com/fesselk/ros_google_sbi.git
```
alternative
```
cd <catkin_ws>/src

git clone https://github.com/fesselk/ros_google_sbi.git ros_google_sbi

cd ros_google_sbi

git submodule update --init --recursive
```

##make
```
cd <catkin_ws>

catkin_make install
```

prior running source your catkin_ws installs setup.sh `source <catkin_ws>/install/setup.sh`

##run server
```
cd <catkin_ws>

roslaunch ros_google_sbi sbi.launch
```

##run client
```
rosrun ros_google_sbi nameit_client -h

rosrun ros_google_sbi nameit_client <filename.jpg>
```
