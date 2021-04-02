
add_subdirectory(pybind11)
pybind11_add_module(kp src/main.cpp)

include_directories(
        ${PROJECT_SOURCE_DIR}/single_include/)

include_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/include)
link_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/lib)
include_directories(/opt/hostedtoolcache/Python/3.9.2/x64/include/python3.9)
        
target_link_libraries(
    kp PRIVATE
    kompute::kompute
    -lvulkan)

