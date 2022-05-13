cmake_minimum_required(VERSION 3.0.2)
project(navigation_msgs)

find_package(catkin REQUIRED
  COMPONENTS
  message_generation
  geographic_msgs
  std_msgs
)

add_message_files(
  DIRECTORY msg
  FILES
  MissionPlan.msg
  StrategicPoint.msg
  MissionContext.msg
  WayPoint.msg
)

add_service_files(
  DIRECTORY srv
  FILES
  PullMission.srv
  PushMission.srv
  CoverageArea.srv
)

generate_messages(
  DEPENDENCIES
  geographic_msgs
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS geographic_msgs std_msgs message_runtime
)