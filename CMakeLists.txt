cmake_minimum_required(VERSION 3.25)
project(LearnOpenGL LANGUAGES CXX)

set(GLFW_ROOT ${CMAKE_SOURCE_DIR}/../glfw-3.4.bin.MACOS)
set(GLAD_ROOT ${CMAKE_SOURCE_DIR}/glad)

add_executable(LearnOpenGL main.cpp)

target_include_directories(LearnOpenGL PRIVATE 
    ${GLFW_ROOT}/include
    ${GLAD_ROOT}/include)

target_link_directories(LearnOpenGL PRIVATE ${GLFW_ROOT}/lib-arm64)

# macOSでGLFWを使うときに必要なframework
target_link_libraries(LearnOpenGL PRIVATE
    "-framework Cocoa"
    "-framework IOKit"
    "-framework CoreVideo"
    "-framework OpenGL"
)