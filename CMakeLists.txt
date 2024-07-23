cmake_minimum_required(VERSION 3.10)
project(OpenVDB_Examples)

# 直接指定C++17标准
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

# Define the directory containing the source files
set(SOURCE_DIR src)

# Use file(GLOB) to collect all .cpp files
file(GLOB CPP_SOURCES "${SOURCE_DIR}/*.cpp")

# Loop over all collected .cpp files
foreach(SOURCE_FILE IN LISTS CPP_SOURCES)
    # Get the filename without path and extension
    get_filename_component(EXECUTABLE_NAME ${SOURCE_FILE} NAME_WE)
    
    # Add an executable for each source file
    add_executable(${EXECUTABLE_NAME} ${SOURCE_FILE})
    
    # Link the libraries
    target_link_libraries(${EXECUTABLE_NAME} ${CONAN_LIBS})
endforeach()