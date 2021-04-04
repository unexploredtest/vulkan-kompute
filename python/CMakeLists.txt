
add_subdirectory(pybind11)
pybind11_add_module(kp src/main.cpp)

include_directories(
        ${PROJECT_SOURCE_DIR}/single_include/)

include_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/include)
link_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/lib)

target_compile_definitions(
    kp PRIVATE kompute::kompute PRIVATE ${VULKAN}
    )

