

include_directories(../)
AUX_SOURCE_DIRECTORY(. MVE_SRCS)

find_package(PNG REQUIRED)


add_library(mve STATIC ${MVE_SRCS})

target_link_libraries(mve PRIVATE PNG::PNG)

set(CMAKE_INSTALL_PREFIX ../../)