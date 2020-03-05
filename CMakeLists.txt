cmake_minimum_required(VERSION 3.8)
project(inotify-cpp)

option(INOTIFY_BUILD_SHARED_LIBS "Build as a shared library" OFF)
option(INOTIFY_BUILD_TESTS "Enable tests" OFF)
option(INOTIFY_BUILD_EXAMPLES "Enable building examples" OFF)

set(INOTIFY_CPP_TYPE STATIC)
if (INOTIFY_BUILD_SHARED_LIBS)
    set(INOTIFY_CPP_TYPE SHARED)
endif()

add_subdirectory(src)

if (INOTIFY_BUILD_EXAMPLES)
    add_subdirectory(example)
endif()

if (INOTIFY_BUILD_TESTS)
    enable_testing()
    add_subdirectory(test)
endif()
