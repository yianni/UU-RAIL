# CMakeLists for the UU-RAIL project
# Initial version 19-05-10
# Chris Burbridge
#
#	Math Library
#
#--------------------------------------
#  Define the sources
#
set(MATH_LIB_SRC  kmeans.cpp Math.cpp)
add_library(UU-RAIL-Math SHARED ${MATH_LIB_SRC})

# The library  requires the libraries discovered in the master
# CMake file.
target_link_libraries(UU-RAIL-Math ${CMAKE_REQUIRED_LIBRARIES})

#--------------------------------------
#   Includes
#
include_directories(. .. Include)


set(CMAKE_REQUIRED_LIBRARIES "UU-RAIL-Math;${CMAKE_REQUIRED_LIBRARIES}")


#--------------------------------------
#   Install directions
# 
install(TARGETS UU-RAIL-Math LIBRARY DESTINATION lib)


#-------------------------------------
# Grab the include directory into the build system too
add_subdirectory(Include)