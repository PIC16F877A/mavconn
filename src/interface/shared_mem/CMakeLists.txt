PIXHAWK_LIBRARY(mavconn_shm SHARED
  SHM.cc
  SHMImageClient.cc
  SHMImageServer.cc
)
PIXHAWK_LINK_LIBRARIES(mavconn_shm
  ${OPENCV_CORE_LIBRARY}
)

SET_TARGET_PROPERTIES(mavconn_shm PROPERTIES COMPILE_FLAGS "-D_REENTRANT")
target_link_libraries(mavconn_shm
  ${OPENCV_CORE_LIBRARY}
  lcm
  mavconn_lcm
)
