cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

add_definitions(-std=c++11)

set(CMAKE_BUILD_TYPE "Debug")
set(CXX_FLAGS "-Wall")
set(CMAKE_CXX_FLAGS, "${CXX_FLAGS}")

project(test)

find_package(PCL 1.7.2 EXACT)

include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})
list(REMOVE_ITEM PCL_LIBRARIES "vtkproj4")

add_executable (pcdxyzi_pcdxyz pcdxyzi_pcdxyz.cpp)
target_link_libraries (pcdxyzi_pcdxyz ${PCL_LIBRARIES})
