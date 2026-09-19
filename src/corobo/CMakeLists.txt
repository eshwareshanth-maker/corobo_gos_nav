cmake_minimum_required(VERSION 3.8)
project(corobo)

find_package(ament_cmake REQUIRED)

install(DIRECTORY urdf worlds config launch rviz
        DESTINATION share/${PROJECT_NAME})

install(PROGRAMS
  scripts/latlon_goal.py
  scripts/latlon_odom.py
  scripts/serial_base.py
  DESTINATION lib/${PROJECT_NAME}
)

ament_package()
