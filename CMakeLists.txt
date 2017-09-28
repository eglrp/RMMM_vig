project(vig)

cmake_minimum_required (VERSION 2.8) 
cmake_policy(SET CMP0015 NEW)

set(CMAKE_CXX_STANDARD 11)

set(CMAKE_CXX_FLAGS "-std=c++11")
set(CMAKE_CXX_FLAGS_RELEASE "-O3 -Wall -g")
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

if ("${CMAKE_BUILD_TYPE}" STREQUAL "")
  set(CMAKE_BUILD_TYPE "Release")
endif()
 
find_package(Eigen REQUIRED)
find_package(Ceres REQUIRED)
find_package(Glog  REQUIRED)

include_directories(${PROJECT_SOURCE_DIR}/include
                    ${EIGEN_INCLUDE_DIR}
                    ${CERES_INCLUDE_DIRS}
                    ${GLOG_INCLUDE_DIR})

include_directories(${CMAKE_CURRENT_BINARY_DIR} )

set(VIG_CORE_SRC rtkcmn.c
                 convkml.c
                 convrnx.c
                 convgpx.c
                 datum.c
                 download.c
                 ephemeris.c
                 geoid.c
                 gis.c
                 ionex.c
                 lambda.c
                 options.c
                 pntpos.c
                 postpos.c
                 ppp.c
                 ppp_ar.c
                 ppp_corr.c
                 preceph.c
                 qzslex.c
                 rcvraw.c
                 rinex.c
                 rtcm.c
                 rtcm2.c
                 rtcm3.c
                 rtcm3e.c
                 rtkpos.c
                 rtksvr.c
                 sbas.c
                 solution.c
                 stream.c
                 streamsvr.c
                 tides.c
                 tle.c
                 rcv/binex.c
                 rcv/crescent.c
                 rcv/gw10.c
                 rcv/javad.c
                 rcv/novatel.c
                 rcv/nvs.c
                 rcv/rcvlex.c
                 rcv/rt17.c
                 rcv/septentrio.c
                 rcv/skytraq.c
                 rcv/ss2.c
                 rcv/ublox.c
                 rcv/cmr.c)


