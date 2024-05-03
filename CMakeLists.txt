cmake_minimum_required(VERSION 3.14)
project(tinyspline_vendor)

find_package(ament_cmake REQUIRED)
find_package(ament_cmake_vendor_package REQUIRED)

ament_vendor(tinyspline
  VCS_URL https://github.com/msteinbeck/tinyspline.git
  VCS_VERSION 5f0e8fad34e86771cfae3dac4beef5f1858d5610 # v0.6.0
  VCS_TYPE git
  CMAKE_ARGS
    -DBUILD_SHARED_LIBS=ON
)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package(
  CONFIG_EXTRAS tinyspline_vendor-extras.cmake
)
