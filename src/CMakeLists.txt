set(LIB_NAME cpp_qr_to_png)

file(GLOB_RECURSE ALL_SOURCES LIST_DIRECTORIES true *.h *.cpp)
list(FILTER ALL_SOURCES EXCLUDE REGEX ".*/main.cpp$")

add_library(${LIB_NAME} STATIC ${ALL_SOURCES})

target_include_directories(${LIB_NAME} PUBLIC 
    ${CMAKE_CURRENT_SOURCE_DIR}
)

target_link_libraries(${LIB_NAME} PUBLIC
    stdc++fs
    tinypngoutput
    qr-code-generator
)
