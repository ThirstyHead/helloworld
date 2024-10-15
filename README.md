# helloworld
Hello World

## Explainy Bits...
The source code is in `main.cpp`. But this isn't _executable_ (runnable) until it gets compiled into an executable.

[CMake](https://cmake.org/) is the tool we'll use to create an executable from our C++ source code. 

### The CMakeLists.txt file
The `CMakeLists.txt` file should contain a few simple commands. Based on those commands, a full `make` build environment is created.

```
cmake_minimum_required(VERSION 3.3)
project(HelloWorld)

add_executable(hello_world main.cpp)
```

### The build directory
If the `build` directory doesn't exist, create it:
```
$ mkdir build
```

Once the `build` directory exists, move to that directory and run `cmake ..`. This creates the `make` environment. 

```
$ cd build
$ cmake ..

CMake Deprecation Warning at CMakeLists.txt:1 (cmake_minimum_required):
  Compatibility with CMake < 3.5 will be removed from a future version of
  CMake.

  Update the VERSION argument <min> value or use a ...<max> suffix to tell
  CMake that the project does not need compatibility with older versions.


-- The C compiler identification is AppleClang 15.0.0.15000309
-- The CXX compiler identification is AppleClang 15.0.0.15000309
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /Library/Developer/CommandLineTools/usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /Library/Developer/CommandLineTools/usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done (2.6s)
-- Generating done (0.0s)
-- Build files have been written to: /Users/scott/code/local/helloworld/build
```

### The make build environment
`CMake` has now created a `make` build environment. 

```
$ ls -al                            (main)helloworld
total 56
drwxr-xr-x   6 scott  staff    192 Oct 15 13:24 .
drwxr-xr-x  10 scott  staff    320 Oct 15 13:15 ..
-rw-r--r--   1 scott  staff  14202 Oct 15 13:24 CMakeCache.txt
drwxr-xr-x  13 scott  staff    416 Oct 15 13:24 CMakeFiles
-rw-r--r--   1 scott  staff   5331 Oct 15 13:24 Makefile
-rw-r--r--   1 scott  staff   1852 Oct 15 13:24 cmake_install.cmake

```

Specifically, the `Makefile` has all of the interesting stuff in it. 

### Making the executable
Finally, we are ready to make an executable from our source code. Type `make` to build the executable. 

```
$ make                          (main)

helloworld
[ 50%] Building CXX object CMakeFiles/hello_world.dir/main.cpp.o
[100%] Linking CXX executable hello_world
[100%] Built target hello_world
```

### Running the executable
Our executable is called `hello_world`. To run it, type `./hello_world`.

```
$ ./hello_world

Hello World!
```
