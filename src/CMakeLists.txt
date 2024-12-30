# Add source files for the `nano` executable
set(SRC_FILES
    browser.c
    chars.c
    color.c
    cut.c
    files.c
    global.c
    help.c
    history.c
    move.c
    nano.c
    prompt.c
    rcfile.c
    search.c
    text.c
    utils.c
    winio.c
)

# Add include directories for `lib` and `m4`
include_directories(${CMAKE_SOURCE_DIR}/lib ${CMAKE_SOURCE_DIR}/m4)

# Add target for the `nano` executable
add_executable(nanopp ${SRC_FILES})

# Add link libraries for `nano`
target_link_libraries(nanopp ${CMAKE_THREAD_LIBS_INIT} ${CMAKE_DL_LIBS})
