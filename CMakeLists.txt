cmake_minimum_required(VERSION 2.8.3)
project(mr_messages)

find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
  message_generation
)

## This macro ensures modules and global scripts declared therein get installed
## See http://ros.org/doc/api/catkin/html/user_guide/setup_dot_py.html
catkin_python_setup()

################################################
## Declare ROS messages, services and actions ##
################################################

## Generate messages in the 'msg' folder
 add_message_files(
   FILES
   ROT.msg
   WIND.msg
   PRESSURE.msg
   N2KInfo.msg
   Heading.msg
   Speed.msg
 )


## Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
  std_msgs
)

################################################
## Declare ROS dynamic reconfigure parameters ##
################################################

###################################
## catkin specific configuration ##
###################################

# add_dependencies(read_n2k ${catkin_EXPORTED_TARGETS})

## CATKIN_DEPENDS: catkin_packages dependent projects also need
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES read_n2k
#  CATKIN_DEPENDS rospy std_msgs
#  DEPENDS system_lib
  CATKIN_DEPENDS message_runtime
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)