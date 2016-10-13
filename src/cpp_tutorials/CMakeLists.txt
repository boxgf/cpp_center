cmake_minimum_required(VERSION 2.8.3)
project(cpp_tutorial)

find_package(catkin REQUIRED COMPONENTS
  roscpp
)

# Add C++11 compiler option
add_definitions(-std=c++11)

catkin_package(
  INCLUDE_DIRS include
  CATKIN_DEPENDS roscpp
)

include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

add_executable(cpp_tutorial_node 
  src/type_casting.cpp
)

target_link_libraries(cpp_tutorial_node
  ${catkin_LIBRARIES}
)

add_dependencies(cpp_tutorial_node
  ${catkin_EXPORTED_TARGETS}
)
