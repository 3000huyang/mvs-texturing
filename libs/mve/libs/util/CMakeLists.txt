

include_directories(../)
AUX_SOURCE_DIRECTORY(. UTIL_SRCS)
add_library(mve_util STATIC ${UTIL_SRCS})