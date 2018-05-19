# SOURCE
set (SRC
  main.cpp 
  Calibration.cpp  Calibration.h
  Calibration_deprecated.cpp 
  )
# SET(OpenCV_DIR /home/phyorch/opencv-3.4.0/build)



# CHECK THE DEPENDENCIES
# GLIB
find_package (Glib REQUIRED)
# GSL
find_package (GSL REQUIRED)
# Opencv
find_package (OpenCV REQUIRED HINTS /home/phyorch/opencv-3.4.0/build)


#if(CMAKE_VERSION VERSION_LESS "2.8.11")
#    # Add OpenCV headers location to your include paths
#    include_directories(${OpenCV_INCLUDE_DIRS})
#endif()

include_directories (${Glib_INCLUDE_DIRS}
  ${GSL_INCLUDE_DIR}
  ${OpenCV_INCLUDE_DIRS}
  ${SRC_DIR}/common 
  )


add_executable (mi-extrinsic-calib ${SRC})

target_link_libraries (mi-extrinsic-calib
        ${Glib_LIBRARIES}
        ${GSL_LIBRARIES}
        ${OpenCV_LIBRARIES}
        common
        )
