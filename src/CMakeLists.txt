cmake_minimum_required(VERSION 3.16)

project(DaduDa VERSION 0.1 LANGUAGES CXX)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Qt6 6.6 COMPONENTS Core Gui Widgets Quick SerialPort REQUIRED)

set(SOURCES main.cpp daduda.cpp) 
set(HEADERS daduda.h)
set(UI daduda.ui)

qt_add_executable(DaduDa
        ${SOURCES}
        ${HEADERS}
        ${UI}
)

set_target_properties(DaduDa PROPERTIES
    MACOSX_BUNDLE_GUI_IDENTIFIER my.example.com
    MACOSX_BUNDLE_BUNDLE_VERSION ${PROJECT_VERSION}
    MACOSX_BUNDLE_SHORT_VERSION_STRING ${PROJECT_VERSION_MAJOR}.${PROJECT_VERSION_MINOR}
    MACOSX_BUNDLE TRUE
    WIN32_EXECUTABLE TRUE
)

target_link_libraries(DaduDa
    PRIVATE Qt6::Quick Qt6::Widgets Qt6::SerialPort)

install(TARGETS DaduDa
    BUNDLE DESTINATION .
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR})
