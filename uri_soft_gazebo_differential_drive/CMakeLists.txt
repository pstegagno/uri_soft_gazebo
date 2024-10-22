cmake_minimum_required(VERSION 2.8.3)
project(uri_soft_gazebo_differential_drive)

## Compile as C++11, supported in ROS Kinetic and newer
add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
#  gazebo_ros
#  roscpp    
#  std_msgs
#  eigen_conversions
#  nav_msgs
#  gazebo_msgs
#  sensor_msgs
#  uri_soft_base
#  message_generation
#  controller_manager
)


#<<<<<<< HEAD
find_package(OpenCV 4 REQUIRED)
message(WARNING ${OpenCV_INCLUDE_DIRS})
#=======
#find_package(OpenCV 3 REQUIRED)
#message(WARNING ${OpenCV_INCLUDE_DIRS})
#>>>>>>> 72b29e2c6dde3eaeec7a5caa71517e28ae327b29



####################################################################################################################
# Setup for python modules and scripts
###############################################################################################

#catkin_python_setup()




###################################################################################################
# Setup for catkin specific configuration to be passed to dependent projects
##############################################################################################
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES myrobot_description
#  CATKIN_DEPENDS message_runtime
#  DEPENDS system_lib
)




foreach(dir meshes urdf src)
   install(DIRECTORY ${dir}/
      DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)




install(DIRECTORY launch save_model
	DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}

)











