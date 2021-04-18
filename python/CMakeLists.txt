
add_subdirectory(pybind11)

pybind11_add_module(kp src/main.cpp)

include_directories(
        ${PROJECT_SOURCE_DIR}/single_include/)

# Adding vulkan headers and vulkan loader that got built
include_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/include)
link_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/lib)

target_link_libraries(
    kp PRIVATE kompute::kompute PRIVATE ${VULKAN}
    )

