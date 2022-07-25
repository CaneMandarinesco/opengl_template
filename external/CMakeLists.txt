# don't know what those do
add_definitions(
	-DTW_STATIC
	-DTW_NO_LIB_PRAGMA
	-DTW_NO_DIRECT3D
	-DGLEW_STATIC
	-D_CRT_SECURE_NO_WARNINGS
)

### GLFW 3.3.8 ###

add_subdirectory (glfw-3.3.8)

include_directories(
	glfw-3.3.8/include/GLFW/
	glew-2.1.0/include/
)

# grup libraries to one variable
set(OPENGL_LIBRARY
	${OPENGL_LIBRARY}
	-lGL -lGLU -lXrandr -lXext -lX11 -lrt
	${CMAKE_DL_LIBS}
	${GLFW_LIBRARIES}
)

### GLEW 2.1.0 ###

set(GLEW_SOURCE
	glew-2.1.0/src/glew.c
)

# ???
set(GLEW_HEADERS
)


# add libs
add_library(GLEW_LIB STATIC
	${GLEW_SOURCE}
	${GLEW_INCLUDE}
)

# bind libs
target_link_libraries(GLEW_LIB
	${OPENGL_LIBRARY}
	${EXTRA_LIBS}
)
