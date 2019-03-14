file (GLOB HEADERS "*.h")
file (GLOB SOURCES "[^_]*.cpp")

set(BIN texrecon)
#include_directories("C:/Users/huyang017/vcpkg/installed/x64-windows/include")
#link_directories("C:/Users/huyang017/vcpkg/installed/x64-windows/debug/lib")
include_directories ( ${TBB_INCLUDE_DIRS} )
message("tbb include dir is " ${TBB_INCLUDE_DIRS} )
link_directories( ${TBB_LIBRARY} )
message("tbb library dir is " ${TBB_LIBRARY} )
add_definitions(-D NOMINMAX)
add_executable(${BIN} ${SOURCES})
set_property(TARGET ${BIN} PROPERTY INTERPROCEDURAL_OPTIMIZATION True)
#add_dependencies(${BIN} ext_mve)


#target_link_libraries(${BIN} tex ${TBB_LIBRARIES} )
target_link_libraries(${BIN} tex  mve mve_util)

install(TARGETS ${BIN} RUNTIME DESTINATION bin)
