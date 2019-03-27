cmake_minimum_required(VERSION 2.8.3)
project(door_state_detection_msgs)


find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  actionlib_msgs
)

add_action_files(
  FILES
  door_state_detection.action
)

generate_messages(
  DEPENDENCIES
  actionlib_msgs
  std_msgs  # Or other packages containing msgs
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES door_state_detection_msgs
   CATKIN_DEPENDS roscpp std_msgs
#  DEPENDS system_lib
)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

install(DIRECTORY include/${PROJECT_NAME}/
 DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
 FILES_MATCHING PATTERN "*.h" PATTERN "*.hpp"
)
