cmake_minimum_required(VERSION 3.25.1)

project(FFTWPlayground)

set(INCLUDES "")
set(LIBS "")

# FFTW
add_subdirectory(external/fftw)
message(STATUS fftw3)
list(APPEND INCLUDES external/fftw/api)
list(APPEND LIBS fftw3)

# Executable build target.
add_executable(fftw_playground src/main.cpp)
target_include_directories(fftw_playground PUBLIC ${INCLUDES})
target_link_libraries(fftw_playground ${LIBS})