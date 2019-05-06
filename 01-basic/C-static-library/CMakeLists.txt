cmake_minimum_required(VERSION 3.5)

project(hello_library)

############################################################
# Create a library
############################################################

# Generate the static library from the library sources
#  with the name libhello_library.a with the sources
add_library(${PROJECT_NAME} STATIC 
    src/Hello.cpp
)

target_include_directories(${PROJECT_NAME}
    PUBLIC 
    	# For public headers it is often a good idea to have your include folder be "namespaced" with sub-directories.
        ${PROJECT_SOURCE_DIR}/include
)


############################################################
# Create an executable
############################################################

# Add an executable with the above sources
add_executable(hello_binary
    src/main.cpp
)

# link the new hello_library target with the hello_binary target
target_link_libraries( hello_binary
    PRIVATE 
        ${PROJECT_NAME}
)
