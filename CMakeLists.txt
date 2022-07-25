cmake_minimum_required (VERSION 3.0)
get_filename_component(PROJECT ${CMAKE_CURRENT_SOURCE_DIR} NAME)
string(REPLACE " " "_" PROJECT ${PROJECT})
project(${PROJECT})

find_package (OpenGL REQUIRED)

# include glew, glfw, glm ecc...
add_subdirectory (external)

# include headers!
include_directories (
	external/glew-2.1.0/include/
	external/glfw-3.3.8/include/
	external/glm/
	.
)

# group all libs to one variabe
set (LIBS 
		${OPENGL_LIBRARY}
		glfw
		GLEW_LIB
)

add_definitions(
	-DTW_STATIC
	-DTW_NO_LIB_PRAGMA
	-DTW_NO_DIRECT3D
	-DGLEW_STATIC
	-D_CRT_SECURE_NO_WARNINGS
)

# create executable
add_executable(${PROJECT} main.cpp)
target_link_libraries(${PROJECT} ${LIBS})

