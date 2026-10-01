cmake_minimum_required(VERSION 3.10)
project(Lab2Project)

# 3. Создаем библиотеку из util (STATIC)
add_library(util_lib STATIC util/util.cpp)

# 2. Используем target_include_directories
target_include_directories(util_lib PUBLIC util)

# 4. Создаем exe, используя библиотеку
add_executable(my_app main.cpp)
target_link_libraries(my_app PRIVATE util_lib)