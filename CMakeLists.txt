cmake_minimum_required(VERSION 3.20)
project(libcsp-freertos)

if(NOT DEFINED FREERTOS_PORT)
  message(STATUS "Auto selecting GCC_POSIX for FREERTOS_PORT")
  set(FREERTOS_PORT GCC_POSIX)
endif()

add_executable(demo)
target_sources(demo PRIVATE
  main.c
  hooks.c
)

add_library(freertos_config INTERFACE)
target_include_directories(freertos_config SYSTEM
  INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})

add_subdirectory(freertos)
add_subdirectory(subprojects/libcsp)

target_link_libraries(demo PRIVATE
  freertos_kernel
  freertos_config
  csp
)
