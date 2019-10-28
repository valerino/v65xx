cmake_minimum_required(VERSION 3.1)
project (v65xx)
set (CMAKE_CXX_STANDARD 11)

add_library (${PROJECT_NAME} SHARED
        CMOS65xx.cpp
        )

include_directories (
        $ENV{EMUSHARED_INCLUDE_PATH}
        )

target_include_directories (${PROJECT_NAME} PUBLIC
        ${PROJECT_SOURCE_DIR}
        )
        
target_link_libraries(${PROJECT_NAME}
        $ENV{EMUSHARED_LIB_PATH}/libemushared.a
        )
