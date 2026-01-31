cmake_minimum_required(VERSION 4.1)
if(CMAKE_SIZEOF_VOID_P EQUAL 8) # If 64bit
    file(GLOB LIBS 64bit/*.lib)
endif()

if(UNIX)
    file(GLOB LIBS lib/*.so)
endif()

add_library(ffmpeg INTERFACE)
target_link_libraries(ffmpeg INTERFACE ${LIBS})
target_include_directories(ffmpeg INTERFACE include)
