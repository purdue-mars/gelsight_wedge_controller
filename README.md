# gelsight_wedge_controller

ROS control interface with Dynamixel library to control the Gelsight Wedge Gripper

## Quick start
1. Add dependency ROS packages
- [DynamixelSDK](https://github.com/ROBOTIS-GIT/DynamixelSDK)
- [Dynamixel interface](https://github.com/csiro-robotics/dynamixel_interface)
2. Update config in `config/controller_cfg.yaml` to match your gripper open/close encoder count params
3. Build + source
4. Run `roslaunch gelsight_wedge_controller gripper.launch`
5. In another tab,
- Close: 
```
rostopic pub /desired_joint_states sensor_msgs/JointState '{name: ['gripper_joint'], position: [2.2],velocity: [-0.5]}' --once
```
- Open: 
```
rostopic pub /desired_joint_states sensor_msgs/JointState '{name: ['gripper_joint'], position: [0],velocity: [0.5]}' --once
```
