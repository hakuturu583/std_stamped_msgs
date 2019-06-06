cmake_minimum_required(VERSION 2.8.3)
project(std_stamped_msgs)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  std_msgs
)

add_message_files(
  FILES
  BoolStamped.msg
  ByteMultiArrayStamped.msg
  ByteStamped.msg
  CharStamped.msg
  ColorRGBAStamped.msg
  DurationStamped.msg
  EmptyStamped.msg
  Float32Stamped.msg
)

generate_messages(
  DEPENDENCIES
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS message_runtime std_msgs
)

foreach(dir msg)
  install(DIRECTORY ${dir}/
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)