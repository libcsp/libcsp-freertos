cmake_minimum_required(VERSION 3.20)
project(libcsp-freertos)

add_executable(demo)
target_sources(demo PRIVATE
  main.c
  hooks.c
  freertos/list.c
  freertos/queue.c
  freertos/tasks.c
  freertos/timers.c
  freertos/portable/ThirdParty/GCC/Posix/port.c
  freertos/portable/ThirdParty/GCC/Posix/utils/wait_for_event.c)
target_include_directories(demo PRIVATE
  .
  freertos/include
  freertos/portable/ThirdParty/GCC/Posix)
target_link_libraries(demo PRIVATE csp)

add_subdirectory(subprojects/libcsp)
