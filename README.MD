

- CMAKE_CURRENT_SOURCE_DIR：当前正在处理的源目录的路径.
- CMAKE_SOURCE_DIR： 最外层CMakeLists.txt所在目录

按文件类型修改默认输出路径
CMake 提供了一些预定义的变量来控制不同类型文件的默认输出路径，常见的有：

- CMAKE_ARCHIVE_OUTPUT_DIRECTORY 表示静态库的默认输出路径
- CMAKE_LIBRARY_OUTPUT_DIRECTORY 表示linux上动态库（*.so）的输出路径
- CMAKE_RUNTIME_OUTPUT_DIRECTORY 表示可执行程序，以及windows上动态库（*.dll）的输出路径
- CMAKE_PDB_OUTPUT_DIRECTORY 表示MSVC环境下pdb文件的输出路径

修改target的输出路径

- ARCHIVE_OUTPUT_DIRECTORY
- LIBRARY_OUTPUT_DIRECTORY
- RUNTIME_OUTPUT_DIRECTORY
- PDB_OUTPUT_DIRECTORY

```cmake
add_executable(abc main.cpp)
set_target_properties(abc PROPERTIES 
    RUNTIME_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}/bin")

add_library(foo SHARED foo.cpp foo.h)
set_target_properties(foo PROPERTIES 
    RUNTIME_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}/bin"
    LIBRARY_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}/lib")
```


设置编译器

```c


set (CMAKE_C_COMPILER "D:/Program Files/LLVM/bin/gcc")
 
set (CMAKE_CXX_COMPILER "D:/Program Files/LLVM/bin/g++")

```