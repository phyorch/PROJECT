project (mi-extrinsic-calib)


SET(CMAKE_CXX_STANDARD_REQUIRED ON)
SET (CMAKE_CXX_STANDARD 17)

ADD_DEFINITIONS(-lstdc++)


# CMAKE TWEAKS
#========================================================================
cmake_minimum_required (VERSION 2.6)

#These variables will be inherited in child directories
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/Modules/")
set (SRC_DIR "${CMAKE_SOURCE_DIR}/src")



set (EXECUTABLE_OUTPUT_PATH
  "${PROJECT_SOURCE_DIR}/bin"
  CACHE PATH
  "Single directory for all executables."
  )

set (LIBRARY_OUTPUT_PATH
  "${PROJECT_SOURCE_DIR}/lib"
  CACHE PATH
  "Single directory for all executables."
  )



# COMPILE THE SOURCE
#========================================================================
ADD_SUBDIRECTORY(${CMAKE_CURRENT_SOURCE_DIR}/src)
