cmake_minimum_required(VERSION 2.8.3)
project(trial)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  roscpp
)

catkin_package(
    INCLUDE_DIRS include
    LIBRARIES trial
    CATKIN_DEPENDS roscpp
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

add_executable(HelloWorld nodes/HelloWorld.cpp)

target_link_libraries(HelloWorld
    ${catkin_LIBRARIES}
)

install(TARGETS HelloWorld
    ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
    LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
    RUNTIME DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
)
