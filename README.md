# ZDoom
This project is no longer being actively maintained. You probably want to check out [GZDoom](https://github.com/coelckers/gzdoom), which is where all new development is happening.

## CROSS-COMPILE for ARM (WIP-NO_OPEANL)

**1. Build native tools & gdtoa**

- dependendecies: libsdl2-dev
```
mkdir build && cd build
cmake -DNO_OPENAL=ON ..
make
```
**2. Grab generated `ImportExecutables.cmake`**
```
mv ImportExecutables.cmake ..
cd ..
```
**3. Build target cross-compilation binary**
```
mkdir build2 && cd build2
cmake -DFORCE_CROSSCOMPILE=YES -DCMAKE_C_COMPILER:FILEPATH=/opt/miyoo/usr/bin/arm-linux-gcc -DNO_OPENAL=ON -DIMPORT_EXECUTABLES="../ImportExecutables.cmake" -DCMAKE_C_FLAGS="-Ofast -lfts" ..
make
```
