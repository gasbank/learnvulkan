cmake_minimum_required(VERSION 3.22)
project(learnvulkan)

set(CMAKE_CXX_STANDARD 17)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(glfw-3.3.8)

add_executable(learnvulkan main.cpp)
if(LINUX)
target_include_directories(learnvulkan PUBLIC /home/gb/VulkanSDK/1.3.231.2/x86_64/include)
target_link_directories(learnvulkan PUBLIC /home/gb/VulkanSDK/1.3.231.2/x86_64/lib)
endif(LINUX)
if(APPLE)
    target_include_directories(learnvulkan PUBLIC /Users/gb/VulkanSDK/1.3.231.1/macOS/include)
    target_link_directories(learnvulkan PUBLIC /Users/gb/VulkanSDK/1.3.231.1/macOS/lib)
endif(APPLE)
target_link_libraries(learnvulkan glfw vulkan)