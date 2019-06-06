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
  Float32MultiArrayStamped.msg
  Float64Stamped.msg
  Float64MultiArrayStamped.msg
  Int16Stamped.msg
  Int16MultiArrayStamped.msg
  Int32Stamped.msg
  Int32MultiArrayStamped.msg
  Int64Stamped.msg
  Int64MultiArrayStamped.msg
  Int8Stamped.msg
  Int8MultiArrayStamped.msg
  StringStamped.msg
  UInt16Stamped.msg
  UInt16MultiArrayStamped.msg
  UInt32Stamped.msg
  UInt32MultiArrayStamped.msg
  UInt64Stamped.msg
  UInt64MultiArrayStamped.msg
  UInt8Stamped.msg
  UInt8MultiArrayStamped.msg
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