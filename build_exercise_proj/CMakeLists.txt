cmake_minimum_required(VERSION 3.10)
project(
    build_exercise 
    LANGUAGES CXX
    VERSION 1.0.0
)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON) 

set(_INC_FOLDER_NAME include) 
set(_INC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/${_INC_FOLDER_NAME}) 
set(_SRC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src) 


add_executable( 
    ${PROJECT_NAME}      
        ${_SRC_DIR}/main.cpp 
)

add_subdirectory(libs)

target_link_libraries(${PROJECT_NAME} PRIVATE tools_lib_proj)

target_link_directories(${PROJECT_NAME} PRIVATE tools_lib_proj) 

target_link_libraries( 
    ${PROJECT_NAME} tools  
) 
# for the change