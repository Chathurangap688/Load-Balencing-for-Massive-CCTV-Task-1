cmake_minimum_required(VERSION 3.1)
# Enable C++11
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)
set(CMAKE_WITH_CUDA FALSE)

project( client )
find_package( OpenCV REQUIRED )
add_executable( client cpu_usage.cpp )
# add_executable( server server.cpp )
target_link_libraries( client ${OpenCV_LIBS})
SET(CMAKE_THREAD_LIBS_INIT "${CMAKE_THREAD_LIBS_INIT} -std=c++11 -pthread")

target_link_libraries( client ${CMAKE_THREAD_LIBS_INIT}) 
