cmake_minimum_required(VERSION 2.8.3)
project(buildit_msgs)
find_package(catkin REQUIRED message_generation message_runtime visualization_msgs geometry_msgs std_msgs )

add_message_files(
   FILES
   MountPointMarker.msg
)

add_service_files(
  FILES
  GetInteractiveMarkers.srv
  InteractiveMountPoint.srv
  SetOrientation.srv
  SetPosition.srv
  UpdateInteractiveMountPoint.srv
)

generate_messages(
   DEPENDENCIES
   std_msgs geometry_msgs visualization_msgs
 )

catkin_package(

)

install(DIRECTORY msg/ srv/ DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})
