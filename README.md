# UR5E_robot_advanced_forward_kinematic_system
'Forward_kin_v1.py' in this repository contains the advanced forward kinematic computing system of the UR5E robot. I think no one has done this kind of job before, hoping to help those in need.\
The principle is based on coordinate transformation and matrix calculation. By entering the angle of the joint angles of UR5e, the detailed coordinates of up to 48 points around the robot arm can be calculated, as shown by the yellow dots in the figure below. 
<img src="https://github.com/wq13552463699/UR5E_robot_advanced_forward_kinematic_system/blob/main/Pic/Picture1.jpg" height="500" width="200" >
<img src="https://github.com/wq13552463699/UR5E_robot_advanced_forward_kinematic_system/blob/main/Pic/Picture2.jpg" height="500" width="200" >\
These point coordinates can basically describe the position information of the key parts of the robot during the movement.
  
## Installation
  numpy + Forward_kin_v1.py
  
## Potential application
In order to ensure that the robot can work within a specific range during autonomous work condition of the robot. The robot can automatically reset or call back by functions after touching specific boundaries. For example, reinforcement learning training requires the robot to be trained within a range. If any part of the robot's body exceeds this safety range, the robot must stop working and reset or call back.\
Please see the video below. I use my hand to push the robot so that it touches the safety boundary I set in advance.\
https://www.youtube.com/watch?v=7QEbURsEXJI
The robot can reset itself everytime when it touched the boundary.

## Different from this system and in-built UR5E safety boundary
the built-in safety boundary will force the robot to stop when it is touched, and the robot will not be able to work again without manual recovery. The existence of this system allows the robot to perform specific human instructions (such as callback or reset) before being forced to stop. Another difference is that according to my test, the built-in safety boundary of UR5E is invalid for the Wrist joint of the robot, which means that the Wrist joint can freely enter and exit the safety boundary, which is a big safety hazard.\

## Others
I have used this system for reinforcement learning training. I set a safety boundary as the final protection in the built-in settings of UR5e, and set a second sub-safety boundary within the safety boundary. The area between these two boundaries is the buffer, as long as any point on the robot body entering the buffer, robot will be reset.\
I have tested the effectiveness of the entire system. The error on the UR5 robot in the simulator is within 0.5%. For the application on the real robot, I haven't seen any visiable problems. But in order to ensure that your machine is not damaged, please check it properly before using it.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change\
Please make sure to update tests as appropriate.
