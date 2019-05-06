# Set the minimum version of CMake that can be used
# To find the cmake version run
# $ cmake --version
cmake_minimum_required(VERSION 3.5)

# Set the project name
project (hello_headers)

# Create a sources variable with a link to all cpp files to compile
set(SOURCES
    src/Hello.cpp
    src/main.cpp
)

# Add an executable with the above sources
add_executable(${PROJECT_NAME} ${SOURCES})

# Set the directories that should be included in the build command for this target
# when running g++ these will be included as -I/directory/path/
target_include_directories(${PROJECT_NAME}
    PRIVATE 
        ${PROJECT_SOURCE_DIR}/include
)

message("*** User output ***")
# The root source directory.
message( ${CMAKE_SOURCE_DIR})
# The current source directory if using sub-projects and directories.
message( ${CMAKE_CURRENT_SOURCE_DIR} )
# The source directory of the current cmake project.
message( ${PROJECT_SOURCE_DIR})
# The root binary / build directory. This is the directory where you ran the cmake command.
message( ${CMAKE_BINARY_DIR})
# The build directory you are currently in.
message( ${CMAKE_CURRENT_BINARY_DIR})
# The build directory for the current project.
message( ${PROJECT_BINARY_DIR})

message("*** End ***")