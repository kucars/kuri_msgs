cmake_minimum_required(VERSION 2.8.3)
project(kuri_msgs)

find_package(catkin REQUIRED COMPONENTS 
  roscpp
  rospy
  std_msgs 
  sensor_msgs 
  geometry_msgs
  nav_msgs
  message_generation
  actionlib_msgs)
  
include_directories(
  include
  ${catkin_INCLUDE_DIRS}
  )

add_message_files(
   DIRECTORY msg
   FILES
   Object.msg
   Objects.msg
   ObjectsMap.msg
)

generate_messages(DEPENDENCIES
  std_msgs
  geometry_msgs
  sensor_msgs
  nav_msgs
  )

catkin_package(CATKIN_DEPENDS 
  message_runtime 
  geometry_msgs 
  std_msgs
  nav_msgs
  )