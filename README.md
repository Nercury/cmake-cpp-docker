# Docker images for CLang/GCC and CMake

Docker image of various C++ compilers bundled with latest CMake version.

Current CMake version: 3.6.0.

Each compiler version has a tag associated with it:

- clang-3.4
- clang-3.5
- clang-3.6
- clang-3.7
- clang-3.8
- gcc-4.7
- gcc-4.8
- gcc-4.9
- gcc-5.2
- gcc-6.1

As an example, to compile a project with, say, gcc-5.2, you can do:

```bash
docker run -v `pwd`:/opt -w=/opt nercury/cmake-cpp:gcc-5.2 /bin/bash -c "mkdir build && cd build && cmake .. && make"
```
