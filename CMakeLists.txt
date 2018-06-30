cmake_minimum_required(VERSION 2.8.3)
project(obindex)

find_package(catkin_simple REQUIRED)
catkin_simple(ALL_DEPS_REQUIRED)

############
# BINARIES #
############
add_definitions(-std=c++11)

cs_add_library(${PROJECT_NAME}
    src/Timer.cpp
    src/BinaryIndex.cpp
)

#############
# QTCREATOR #
#############
FILE(GLOB_RECURSE LibFiles "include/*")
add_custom_target(headers SOURCES ${LibFiles})

##########
# EXPORT #
##########
cs_install()
cs_export()
