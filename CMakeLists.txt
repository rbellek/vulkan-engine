cmake_minimum_required(VERSION 3.18)

project(VulkanEngine VERSION 1.0.0)

file(GLOB SRC_FILES ${PROJECT_SOURCE_DIR}/src/*.cpp)

add_executable(${PROJECT_NAME} ${SRC_FILES})