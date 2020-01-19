cmake_minimum_required(VERSION 3.9)

#add_compile_options(-Wall)

add_executable(intro test/main.cpp)
target_compile_features(intro PRIVATE cxx_lambda_init_captures)