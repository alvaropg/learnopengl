cmake_minimum_required(VERSION 3.0)

project(LEARNGL)

find_package(PkgConfig)
pkg_check_modules(GL REQUIRED glfw3)

add_executable(01-hello-window
  src/glad.c
  src/01-hello-window.c)
target_include_directories(01-hello-window PUBLIC
  ${GL_INCLUDE_DIRS}
  ${CMAKE_CURRENT_SOURCE_DIR}/include)
target_link_libraries(01-hello-window dl ${GL_LDFLAGS})
