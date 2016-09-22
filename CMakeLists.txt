cmake_minimum_required (VERSION 2.6)
project (md5)

include_directories (.)

add_library(md5 STATIC md5.h md5.c)
add_executable(md5_test md5_test.c md5.c md5.h)
target_link_libraries(md5_test md5)

enable_testing()
add_test (NAME md5 COMMAND md5_test WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
