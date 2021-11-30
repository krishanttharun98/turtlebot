# TURTLEBOT CONTROLLER ASSIGNMENT-1
### AIM
Assignment-1 is a python script for achieving the given robot's behaviour by driving around the given circuit in the counter-clockwise direction. It has to avoid touching the golden tokens and when close to silver token, it should grab it, move it behind itself and continue on its course of path.
### METHODOLOGY OF THE ROBOT 
###### 1. Robot drives :
Firstly in order to move the robot forward a function called ***DRIVE()*** has been defined. This function has two motors to activate mo and m1. when a set of values is given to the motors, the robot moves forward if it is (+), else drives backward for (-).
###### 2. Robot Turns:
Secondly to turn the robot a fucntion called ***TURN()*** has been defined. This Function is used to turn the robot's motors mo and m1 assigning same amount of speed to both the motors but each diferent in direction to each other to turn the robot.
###### 3.Robot commands: 
In order for the robot to see, grab and release no fucntions are needed. Instead the commands can be used as : R.see(), R.grab(), R.release() for the said tasks to happen.
NOTE - R is the robot() which defines those functionalities in the Robot() folder.
###### 4.Silver Token recognision:
A function ***find_silver_token*** is created with variables, d_silver_token = distance from the silver token to robot, angle_silver_token = postion of the silver token oriented with respect to the robot. If the token.dist returns d_silver_token and token.rot_y returns angle_silver_token then the token is silver. if the d_silver_token less than threshold distance( minimum distance assigned for the robot grab silver token) and absolute angle of angle_silver_token less than angle_thr (angle to allign the robot with the silver token to grab) is both satisfied the robot will grab the silver token, turn and place it behind itself and turns again. A second threshold distance is created to allign the robot with the silver token. If Second threshold distance (d_thr2) is greater than d_silver_token then it allign itself with silver token respect to the angle_silver_token and angle_thr condtions.
###### 5.Golden token recognision:
As the robot should avoid the golden token, four functions are created naming ***find_left_golden_token()***, ***find_right_golden_token()***, ***find_front_golden_token()*** and ***find_golden_token()*** . These functions are created with respective parameters such as : distance of the robot from the respective golden token(front, left and right) and angle fo the robot with respect to the respective golden token (front, left, right).If the distance from the front golden token is lesser than the d_front_thr ( minimum distance from which the robot should avoid the golden tokens), robot should prioritise which side it should turn.For that decision making, a fucntion ***chosse_turn()*** is called. If distance from robot to right golden token is lesser than distance from robot to left golden token then the robot should turn left or else turn right. In front, left, right golden token functions respective range of angles are given for orientation of the robot to visualise the golden token and avoid them.
### RESULT
Code is in assignment1.py and can be run using ***python run.py assignment 1.py.*** Robot follows the path specified in the environment
