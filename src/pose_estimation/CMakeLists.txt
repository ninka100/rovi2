cmake_minimum_required(VERSION 2.6 FATAL_ERROR)
project(pose_estimation)
find_package(PCL 1.3 REQUIRED)
include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

add_executable(icp src/icp.cpp)
target_link_libraries(icp ${PCL_LIBRARIES})
add_executable(ransac_global_alignment src/ransac_global_alignment.cpp)
target_link_libraries(ransac_global_alignment ${PCL_LIBRARIES})
add_executable(segment_plane src/segment_plane.cpp)
target_link_libraries(segment_plane ${PCL_LIBRARIES})
