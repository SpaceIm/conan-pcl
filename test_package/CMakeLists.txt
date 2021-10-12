cmake_minimum_required(VERSION 3.8)
project(test_package)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

find_package(PCL REQUIRED surface CONFIG)

add_executable(${PROJECT_NAME} test_package.cpp)
target_compile_features(${PROJECT_NAME} PUBLIC cxx_std_14)
target_link_libraries(${PROJECT_NAME} PRIVATE PCL_SURFACE_LIBRARIES)
