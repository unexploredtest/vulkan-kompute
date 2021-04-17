# set(Python_FIND_IMPLEMENTATIONS CPython)
# find_package(Python COMPONENTS Interpreter Development.Module REQUIRED)
add_subdirectory(pybind11)

pybind11_add_module(kp src/main.cpp)

include_directories(
        ${PROJECT_SOURCE_DIR}/single_include/)

include_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/include)
link_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/lib)

target_link_libraries(
    kp PRIVATE kompute::kompute PRIVATE ${VULKAN}
    )

