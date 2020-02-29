cmake_minimum_required(VERSION 3.10)
project(yapdatabasecpp VERSION 1.0.0 LANGUAGES CXX DESCRIPTION "YapDatabase CPP Library")

add_library(yappdatabasecpp SHARED src/sqlite3.c)

set_target_properties(yappdatabasecpp PROPERTIES VERSION ${PROJECT_VERSION})
set_target_properties(yappdatabasecpp PROPERTIES SOVERSION 1)

target_include_directories(yappdatabasecpp PRIVATE .)

target_include_directories(yappdatabasecpp PRIVATE include)
target_include_directories(yappdatabasecpp PRIVATE src)

include(GNUInstallDirs)

install(TARGETS yappdatabasecpp
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})
    
