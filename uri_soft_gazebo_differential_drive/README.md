Setting up the package:
put the package under ~/catkin_ws/src
$ cd catkin_ws
$ catkin_make

testing the package:
	$ roscore	
	
	Open gazebo with models:
		$ roslaunch uri_soft_4wd_sim main.launch
		(current two 4wd and wall on the screen)
	or
		$ roslaunch uri_soft_4wd_sim round.launch
		(two two wheel drivers on the screen)
	
	current we have three scripts under folder "src":
	1. $ rosrun uri_soft_4wd_sim control.py
		the second car will move forward, if leaser sensor detects any object inside 1 			meter, the car will move away from the object
	2. $ rosrun uri_soft_4wd_sim keyboard.py:
		use the keyboard to move the first car(with blue block on top) around
		q/z increase/decrease speed
		i/, forward/backward  
		...
	3. $ rosrun uri_soft_4wd_sim follow.py
		the second car will follow the first car in the range of 0.3-0.5 meter
		(currently only follow in stright line)
	4. $ rosrun uri_soft_4wd_sim blockcontrol.py
		the first car will move to given position without crashing on second car
	
Inside the package:
	Under the urdf folder, two cars' model: 
		fourWD.xacro  
		twowd.xacro
		wheel.urdf.xacro (the wheel model being used in the fourWD) 
		wall.urdf 	(blue wall around)
	world folder:
		myworld.world  (gazebo empty world, sun, sky, ground)

if gazebo is not right somehow.. 
$ killall gzserver
$ killall gzclient

