cmake_minimum_required(VERSION 3.0)
project(MyProject)

set(CMAKE_CXX_STANDARD 20)

# 添加 Catch2 子模块
add_subdirectory(third_party/Catch2)

# 添加主程序
add_executable(MyApp main.cpp)

# 链接 Catch2 提供的 target
target_link_libraries(MyApp PRIVATE Catch2::Catch2WithMain)

# 注册单元测试（可选）
include(CTest)
include(Catch)
catch_discover_tests(MyApp)