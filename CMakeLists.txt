cmake_minimum_required(VERSION 3.22)
project(untitled)

set(CMAKE_CXX_STANDARD 17)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(glfw-3.3.8)

add_executable(untitled main.cpp)
target_include_directories(untitled PUBLIC /home/gb/VulkanSDK/1.3.231.2/x86_64/include)
target_link_directories(untitled PUBLIC /home/gb/VulkanSDK/1.3.231.2/x86_64/lib)
target_link_libraries(untitled glfw vulkan)