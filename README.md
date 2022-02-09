# Cmake Runner
A small bash script that allows you to compile and run c/c++ targets withing a CMake project for when you're away from your IDE.

**Limitations:**
* Target file has to end with `.o` extension
* All targets have to have the output directory `out`
* Script has to be run in the same directory as the main `CMakeLists.txt` file

### Example Project Structure and CMake File
``` 
.
├── CMakeLists.txt
├── compile.sh
├── src
    └── hello_world.cpp
```
``` cmake
cmake_minimum_required(VERSION 3.21)
project(globalProject)

set(source_dir ".")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${source_dir}/../../out/)

add_executable(hello_world.o ${source_dir}/hello_world.cpp)

```

### Other
You can make vim automatically call this script by adding the following to your vimrc 
``` vim
map <F8> :!bash compile.sh % <enter>
```

