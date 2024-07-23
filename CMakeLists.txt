cmake_minimum_required(VERSION 3.10)
project(OpenVDB_Examples)

# 直接指定C++17标准
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

add_executable(demo1_HelloWorld demo1.cpp)
target_link_libraries(demo1_HelloWorld ${CONAN_LIBS})

add_executable(demo2CreateGrid demo2CreateGrid.cpp)
target_link_libraries(demo2CreateGrid ${CONAN_LIBS})

add_executable(demo3MakeSphere demo3MakeSphere.cpp)
target_link_libraries(demo3MakeSphere ${CONAN_LIBS})

add_executable(demo4 demo4.cpp)
target_link_libraries(demo4 ${CONAN_LIBS})