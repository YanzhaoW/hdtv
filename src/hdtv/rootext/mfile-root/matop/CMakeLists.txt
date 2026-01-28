add_library(matop SHARED)
target_sources(
    matop
    PRIVATE matop_adjust.c matop_conv.c matop_project.c
    PUBLIC
        FILE_SET HEADERS
            BASE_DIRS ${CMAKE_CURRENT_SOURCE_DIR}
            FILES matop_adjust.h matop_conv.h matop.h matop_project.h
)
target_link_libraries(matop PRIVATE mfile)

install(
    TARGETS matop
    FILE_SET HEADERS
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    PUBLIC_HEADER DESTINATION include
)
