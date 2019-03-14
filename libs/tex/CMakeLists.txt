file (GLOB HEADERS "*.h")
file (GLOB SOURCES "[^_]*.cpp")


include_directories ( ${TBB_INCLUDE_DIRS} )
link_directories( ${TBB_LIBRARY_DIRS} )
add_definitions(-D NOMINMAX)

set(LIBRARY tex)
add_library(${LIBRARY} STATIC ${SOURCES})
set_property(TARGET ${LIBRARY} PROPERTY INTERPROCEDURAL_OPTIMIZATION True)
add_dependencies(${LIBRARY}  ext_rayint ext_eigen ext_mapmap)
target_link_libraries(${LIBRARY}  ${JPEG_LIBRARIES} ${PNG_LIBRARIES} ${TIFF_LIBRARIES})
install(TARGETS ${LIBRARY} ARCHIVE DESTINATION lib)
