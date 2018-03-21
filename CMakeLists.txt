cmake_minimum_required(VERSION 3.9)
project(graphics C)

set(CMAKE_C_STANDARD 11)

add_library(graphics graphics.c graphics.h)
target_link_libraries(graphics SDL SDL_net SDL_ttf)
