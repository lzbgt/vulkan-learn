cmake_minimum_required(VERSION 3.10)

project(VulkanDemo)

set(CMAKE_CXX_STANDARD 17)

# Find Vulkan SDK
find_package(Vulkan REQUIRED)
find_package(glfw3 REQUIRED)
find_package(glm REQUIRED)

# Include directories
include_directories(${Vulkan_INCLUDE_DIRS} ${GLFW3_INCLUDE_DIRS} ${GLM_INCLUDE_DIRS})

link_directories(${Vulkan_LIBRARY_DIRS} "/opt/homebrew/Cellar/glm/1.0.1/lib/")

# Source files
set(SOURCES src/main.cpp)

# Create executable
add_executable(VulkanDemo ${SOURCES})

# Link libraries
target_link_libraries(VulkanDemo Vulkan::Vulkan glfw glm)