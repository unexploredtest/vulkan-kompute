
add_subdirectory(pybind11)
pybind11_add_module(kp src/main.cpp)

include_directories(
        ${PROJECT_SOURCE_DIR}/single_include/)

#include_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/include)
#link_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/lib)
#find_library(VULKAN_SDK
    #NAMES vulkan
    #HINTS "${CMAKE_PREFIX_PATH}/VULKAN_SDK/lib"
#)

target_link_libraries(
    kp PRIVATE kompute::kompute PRIVATE vulkan
    )

