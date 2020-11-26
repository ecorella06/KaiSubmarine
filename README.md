# Open source simulator for a general purpose underwater robot

This repository was used to generate a simulator, for the KAI submarine, used by the Integrated Engineering Group of the University of La Coruña. 

It contains the elements that allow simulating a submarine, inside a water world.

For its implementation, Gabezo and ROS were used, and the modeling was done in Solidworks and then the mesh was converted using Blender. 

To control the submarine within the simulation was used a joystick, which is the same used in the test submarines. 

The project was developed in Ubuntu. It is necessary to install Gazebo and ROS, whose version used was melodic.

## Preparation of the environment 

The following commands are used to the preparation of the environment:

```bash
$git clone https://github.com/ecorella06/KaiSubmarine.git
$cd ..
$catkin_make
```

## Creating a new working environment

```bash
$cd catkin_ws
$source devel/setup.bash
$catkin_make
$source devel/setup.bash
```


## Launch of the simulator

The following commands are used to launch the simulator:

```bash
$roslaunch seabed_world world.launch
$roslaunch uuv_descriptions submarino_kai.launch mode:=default
x:=0 y:=0 z:=-20 namespace:=submarino_kai
```

## Implementation of controls 

By means of the use of the joystick it is possible to control the submarine, in such a way that their behavior is similar to the real robot which is controlled with the same control.

To activate the control it is necessary to call to the package where is the launch file and indicate the model to control.

```bash
$roslaunch uuv_control_cascaded_pid joy_velocity.launch 
uuv_name:=submarino_kae model_name:=submarino_kai joy_id:=0
```
