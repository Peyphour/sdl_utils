cmake_minimum_required(VERSION 3.9)
project(graphics LANGUAGES C VERSION 1.0 DESCRIPTION "multi purpose SDL utils library")
include(GNUInstallDirs)

set(CMAKE_C_STANDARD 11)


add_library(graphics SHARED graphics.c graphics.h)

set_target_properties(graphics PROPERTIES
        VERSION ${PROJECT_VERSION}
        SOVERSION 1
        PUBLIC_HEADER graphics.h)
configure_file(graphics.pc.in graphics.pc @ONLY)
target_include_directories(graphics PRIVATE .)
install(TARGETS graphics
        LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
        PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR})
install(FILES ${CMAKE_BINARY_DIR}/graphics.pc
        DESTINATION ${CMAKE_INSTALL_DATAROOTDIR}/pkgconfig)