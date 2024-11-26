cmake_minimum_required(VERSION 3.30)
project(my_apue3e C)

set(CMAKE_C_STANDARD 11)

include_directories(include)

# 添加公共库源文件
file(GLOB COMMON_LIB_SOURCES lib/*.c)

# 定义一个宏来创建可执行文件
macro(add_my_executable target)
    add_executable(${target} ${ARGN} ${COMMON_LIB_SOURCES})
endmacro()

# 使用宏来创建可执行文件
add_my_executable(main main.c)
add_my_executable(hello intro/hello.c)
add_my_executable(ls1 intro/ls1.c)
add_my_executable(echo intro/echo.c)
add_my_executable(mycat intro/mycat.c)
add_my_executable(getcputc intro/getcputc.c)
add_my_executable(uidgid intro/uidgid.c)
add_my_executable(shell1 intro/shell1.c)
add_my_executable(shell2 intro/shell2.c)
add_executable(testerror intro/testerror.c)
