# toplevel CMakeLists.txt for a catkin workspace
# catkin/cmake/toplevel.cmake

cmake_minimum_required(VERSION 2.8.3)

include(cmake/HunterGate.cmake)
HunterGate(
  URL "https://github.com/ruslo/hunter/archive/v0.21.19.tar.gz"
  SHA1 "5ead1e069b437930d0de8a21824b20fb52b37b50"
)

project(ros)
hunter_add_package(Boost COMPONENTS thread)
hunter_add_package(catkin)
hunter_add_package(rospack)
hunter_add_package(ros_message_runtime)
hunter_add_package(ros_environment)

add_subdirectory(core/rosbuild)
add_subdirectory(core/roslang)
add_subdirectory(core/roslib)
add_subdirectory(ros)
add_subdirectory(tools/rosbash)
add_subdirectory(tools/rosboost_cfg)
add_subdirectory(tools/rosclean)
add_subdirectory(tools/roscreate)
add_subdirectory(tools/rosmake)
add_subdirectory(tools/rosunit)
