cmake_minimum_required(VERSION 2.8.3)
project(rslidar_sync)
find_package(catkin REQUIRED roscpp std_msgs sensor_msgs message_filters)
catkin_package()

include_directories(include
    ${catkin_INCLUDE_DIRS})

add_executable(rslidar_sync_2lidar_node src/timesync_2lidar.cpp)
target_link_libraries(rslidar_sync_2lidar_node
	${catkin_LIBRARIES}
)

add_executable(rslidar_sync_3lidar_node src/timesync_3lidar.cpp)
target_link_libraries(rslidar_sync_3lidar_node
	${catkin_LIBRARIES}
)

install(
  TARGETS rslidar_sync_2lidar_node rslidar_sync_3lidar_node
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})
