
add_subdirectory(pybind11)
unset(PYTHON_EXECUTABLE)
unset(PYTHON_INCLUDE_DIR)
unset(PYTHON_LIBRARY)
unset(PYTHON_VERSION_STRING)
set(Python_FIND_IMPLEMENTATIONS CPython)
find_package(Python COMPONENTS Interpreter Development.Module REQUIRED)

pybind11_add_module(kp src/main.cpp)

include_directories(
        ${PROJECT_SOURCE_DIR}/single_include/)

include_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/include)
link_directories(${CMAKE_SOURCE_DIR}/VULKAN_SDK/lib)

target_link_libraries(
    kp PRIVATE kompute::kompute PRIVATE ${VULKAN}
    )

