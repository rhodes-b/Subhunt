cmake_minimum_required(VERSION 3.1)

project(subhunt)

if (WIN32)
link_directories(./libs/windows)
link_libraries(-lglew32s)
link_libraries(-lglfw3_mt)
endif (WIN32)

if (UNIX)
# link_directories(./libs/linux)
link_libraries(-lGLEW)
link_libraries(-lglfw3)

link_libraries(-ldl)
link_libraries(-lGL)
link_libraries(-lX11)
link_libraries(-lpthread)
endif (UNIX)

link_libraries(-llua)


install( DIRECTORY lua/ DESTINATION ${CMAKE_BINARY_DIR}/lua)
add_executable(${PROJECT_NAME} subhunt.cpp)