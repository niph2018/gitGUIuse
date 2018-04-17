cmake_minimum_required(VERSION 2.8)
#cmake
set(PROJECT_NAME TEST_AL)
project(${PROJECT_NAME})
set(ROOT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/../../)
set(LIB_PATH ${ROOT_PATH}Release/src/)
message(STATUS"library PATH: ${LIB_PATH}")

set(CMAKE_BUILD_TYPE Debug)
set(CMAKE_C_FLAGS_DEBUG "-g -fPIC")
set(CMAKE_CXX_FLAGS_DEBUG "-g -fPIC -std=c++11")

include_directories(${ROOT_PATH}../../../lib/include)

add_executable(test_al test_al.c)

find_library(LIBDMCAM dmcam PATH ${LIB_PATH})

target_link_libraries(test_al ${LIBDMCAM})



