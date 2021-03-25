cmake_minimum_required(VERSION 2.6)
project(pcl_test)
project(voxel_grid)

find_package(PCL 1.2 REQUIRED)

include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

add_executable(pcl_test pcl_test.cpp)

target_link_libraries (pcl_test ${PCL_LIBRARIES})
add_executable (voxel_grid voxel_grid.cpp)
target_link_libraries (voxel_grid ${PCL_LIBRARIES})
SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR})

install(TARGETS pcl_test RUNTIME DESTINATION bin)
install(TARGETS voxel_grid RUNTIME DESTINATION bin)
