cmake_minimum_required(VERSION 2.8.3)
project(needybot_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  rospy
  actionlib_msgs
  geometry_msgs 
  sensor_msgs
  std_msgs
)

add_message_files(
  DIRECTORY
    msg
  FILES
    Altitude.msg
    Base64Image.msg
    Battery.msg
    Date.msg
    SpeechParam.msg
    Path.msg
    Point2D.msg
    Safety.msg
    UIResponse.msg
)

add_action_files(
  DIRECTORY
    action
  FILES
    Animator.action
    Speech.action
)

generate_messages(
  DEPENDENCIES
    actionlib_msgs
    geometry_msgs 
    sensor_msgs
    std_msgs
)

catkin_package(
  #LIBRARIES
  #  ${PROJECT_NAME}            
  CATKIN_DEPENDS
    message_runtime
    sensor_msgs
    std_msgs
    rospy
)
