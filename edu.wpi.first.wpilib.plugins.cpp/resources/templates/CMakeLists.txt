project("FRCUserProgram")
cmake_minimum_required(VERSION 3.1 FATAL_ERROR)
find_package(Gazebo REQUIRED)

file(GLOB_RECURSE SRC_FILES src/*.cpp)

include_directories("~/wpilib/simulation/include"
  ${GAZEBO_INCLUDE_DIRS})

link_directories("~/wpilib/simulation/lib")

add_executable(${PROJECT_NAME} ${SRC_FILES})

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 11)
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD_REQUIRED ON)

target_link_libraries(${PROJECT_NAME} wpilibcSim ${GAZEBO_LIBRARIES})
