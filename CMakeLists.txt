cmake_minimum_required(VERSION 3.10)

project(nano VERSION 8.3)

# Add subdirectories
add_subdirectory(src)
add_subdirectory(doc)
add_subdirectory(lib)
add_subdirectory(m4)
add_subdirectory(po)
add_subdirectory(syntax)

# Configuration for building the project
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -DLOCALEDIR=\"${CMAKE_INSTALL_PREFIX}/share/locale\" -DSYSCONFDIR=\"${CMAKE_INSTALL_PREFIX}/etc\"")

# Configuration for installing the project
install(TARGETS nano RUNTIME DESTINATION bin)
