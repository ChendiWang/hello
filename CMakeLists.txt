cmake_minimum_required(VERSION 3.10)
set(PROJECT_NAME  Hello)
project(${PROJECT_NAME})

add_executable(${PROJECT_NAME} main.cpp server.cpp connection.cpp connection_manager.cpp request_handler.cpp request_parser.cpp reply.cpp mime_types.cpp request.hpp)

find_package(Boost 1.58.0 REQUIRED COMPONENTS system filesystem)
find_package(Threads REQUIRED)
include_directories(${Boost_INCLUDE_DIRS})
link_directories(${Boost_LIBRARY_DIRS})
target_link_libraries(${PROJECT_NAME} ${Boost_LIBRARIES})
target_link_libraries(${PROJECT_NAME} -lpthread -lm)

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 11)



