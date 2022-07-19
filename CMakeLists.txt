cmake_minimum_required(VERSION 3.18)

project(VulkanEngine VERSION 1.0.0)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
add_subdirectory(${CMAKE_SOURCE_DIR}/vendors/glfw)

file(GLOB SRC_FILES ${PROJECT_SOURCE_DIR}/src/*.cpp)
file(GLOB HEADER_FILES ${PROJECT_SOURCE_DIR}/include/*.h)

add_executable(${PROJECT_NAME} ${SRC_FILES} ${HEADER_FILES})

find_package(Vulkan REQUIRED)

target_link_libraries(${PROJECT_NAME} glfw Vulkan::Vulkan)

target_include_directories(${PROJECT_NAME} 
PRIVATE ${CMAKE_SOURCE_DIR}/include
PRIVATE ${CMAKE_SOURCE_DIR}/vendors/glm
PRIVATE ${VULKAN_INCLUDE_DIRS})



