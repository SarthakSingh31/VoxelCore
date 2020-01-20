cmake_minimum_required(VERSION 3.9)

target_compile_options(my_library PRIVATE
     $<$<OR:$<CXX_COMPILER_ID:Clang>,$<CXX_COMPILER_ID:AppleClang>,$<CXX_COMPILER_ID:GNU>>:
          -Wall -Wpedantic -Wextra>
     $<$<CXX_COMPILER_ID:MSVC>:
          /W4>)

add_executable(intro test/main.cpp)
target_compile_features(intro PRIVATE cxx_lambda_init_captures)