cmake_minimum_required(VERSION 3.15)

project(slang_subproject_example)

# Note: this example just pulls the head master branch
# for slang, but a real project would very likely pin
# this to a specific tag and only update when ready
# to accept a new version.
include(FetchContent)
FetchContent_Declare(
  slang
  GIT_REPOSITORY https://github.com/MikePopoloski/slang.git
  GIT_SHALLOW ON)
FetchContent_MakeAvailable(slang)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_executable(test main.cpp)
target_link_libraries(test PUBLIC slang::slang)
