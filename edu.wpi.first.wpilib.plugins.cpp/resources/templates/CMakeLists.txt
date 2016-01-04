project("FRCUserProgram")

cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

cmake_policy(SET CMP0060 NEW)

find_package(Gazebo REQUIRED)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

file(GLOB_RECURSE SRC_FILES src/*.cpp)

include_directories("src"
  "~/wpilib/simulation/include"
  ${GAZEBO_INCLUDE_DIRS})

link_directories("~/wpilib/simulation/lib")

add_executable(${PROJECT_NAME} ${SRC_FILES})

target_link_libraries(${PROJECT_NAME} wpilibcSim ntcore  ${GAZEBO_LIBRARIES})
