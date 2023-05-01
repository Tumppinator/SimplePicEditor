cmake_minimum_required(VERSION 3.10)
project(SimplePicEditor LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 17)

if(MSVC)
    add_compile_options(/Zc:__cplusplus)
endif()

set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_PREFIX_PATH "D:/Qt/6.5.0/msvc2019_64")
find_package(Qt6 COMPONENTS Core Gui Widgets REQUIRED)
set(SOURCES
    src/main.cpp
    # Add other source files here
)

set(HEADERS
    include/mainwindow.h
    # Add other header files here
)

set(RESOURCES
    resources/resources.qrc
    # Add other resource files here
)
add_executable(${PROJECT_NAME} src/main.cpp src/mainwindow.cpp include/mainwindow.h)
target_link_libraries(${PROJECT_NAME} PRIVATE Qt6::Core Qt6::Gui Qt6::Widgets)
target_include_directories(${PROJECT_NAME} PRIVATE include)

