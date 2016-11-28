cmake_minimum_required(VERSION 3.3)

enable_testing()

project(winksignals CXX)

# Use C++14
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED_ON)

include_directories("${CMAKE_CURRENT_SOURCE_DIR}")

add_executable(benchmark_test "examples/Benchmark.cpp")
target_compile_definitions(benchmark_test PRIVATE SKIP_BENCHMARK=1)

add_executable(benchmark "examples/Benchmark.cpp")

add_test(
    NAME test_benchmark
    COMMAND ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/benchmark_test
    )
