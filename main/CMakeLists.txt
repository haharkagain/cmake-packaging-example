cmake_minimum_required(VERSION 3.21)
# set(CMAKE_CXX_COMPILER "/MinGW/mingw64/bin/g++.exe") # this is just some windows bs, delete if it's breaking your code
set (CMAKE_CXX_STANDARD 20)

project(main)

add_executable(main main.cpp)

find_package(mylib REQUIRED)

target_link_libraries(main mylib)	# do mylib::mylib if namespace is set when the library is installed
