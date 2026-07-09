cmake_minimum_required(VERSION 3.10)
project(downstream_probe)

find_package(ament_cmake REQUIRED)
find_package(soem_vendor_ros2 REQUIRED)
find_package(soem REQUIRED)

add_executable(probe src/probe.c)
target_link_libraries(probe PRIVATE soem)
install(TARGETS probe DESTINATION lib/${PROJECT_NAME})

if(BUILD_TESTING)
  add_test(NAME probe COMMAND probe)
endif()

ament_package()
