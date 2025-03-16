cmake_minimum_required(VERSION 3.0.2)
project(pseudo_odom)

## Compile as C++11
add_compile_options(-std=c++11)

## Find catkin packages
find_package(catkin REQUIRED COMPONENTS
  roscpp
  gazebo_msgs
  nav_msgs
  tf
  Eigen3
)

## Declare catkin package
catkin_package(
  CATKIN_DEPENDS roscpp gazebo_msgs nav_msgs tf
)

## Include directories
include_directories(
  ${catkin_INCLUDE_DIRS}
  ${EIGEN3_INCLUDE_DIRS}
)

## Add executable
add_executable(pseudo_odom_node src/pseudo_odom.cpp)

## Link libraries
target_link_libraries(pseudo_odom_node
  ${catkin_LIBRARIES}
)