# libcsp with FreeRTOS

This repository is a sample repository to build libcsp against
FreeRTOS Posix/Linux Simulator.

# How to build

## With Meson

```
git clone https://github.com/libcsp/libcsp-freertos
cd libcsp-freertos
git clone https://github.com/FreeRTOS/FreeRTOS-Kernel freertos
mkdir subprojects
git clone https://github.com/libcsp/libcsp subprojects/libcsp
meson setup builddir
ninja -C builddir
```

## With CMake

```
git clone https://github.com/libcsp/libcsp-freertos
cd libcsp-freertos
git clone https://github.com/FreeRTOS/FreeRTOS-Kernel freertos
mkdir subprojects
git clone https://github.com/libcsp/libcsp subprojects/libcsp
cmake -B builddir -GNinja
ninja -C builddir
```
