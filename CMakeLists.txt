cmake_minimum_required (VERSION 2.8)
project (play)

set(SOURCES src/play.cxx src/glad.c)
set(HEADER_FILES include/glad/glad.h include/KHR/khrplatform.h)
add_executable(play ${SOURCES} ${HEADER_FILES} ${OPENGL_INCLUDE_DIRS} ${GLUT_INCLUDE_DIRS})

find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
find_package(glfw3 3.2 REQUIRED)
include_directories(include ${OPENGL_INCLUDE_DIRS}  ${GLUT_INCLUDE_DIRS} /usr/local/include )

target_link_libraries(play ${OPENGL_LIBRARIES} ${GLUT_LIBRARY} glfw)

