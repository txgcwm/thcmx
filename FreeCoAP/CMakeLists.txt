CMAKE_MINIMUM_REQUIRED(VERSION 2.8.9)

set(TOPDIR ${CMAKE_CURRENT_SOURCE_DIR})

#include(${TOPDIR}/cmake/${TOOLCHAIN}.cmake)

set(OUTDIR ${TOPDIR}/cmake_build/out/)
set(BUILDDIR ${TOPDIR}/cmake_build/build)


#SET(CMAKE_BUILD_TYPE "Debug")
#SET(CMAKE_CXX_FLAGS_DEBUG "-g -Wall")

add_compile_options(-Wall -Wno-unused-local-typedefs -O2 -Os -fomit-frame-pointer)
#add_compile_options("--std=c++11")

#add_definitions(-DCOAP_IP6)
#add_definitions(-DSOCK_IP6)
add_definitions(-DCOAP_DTLS_EN)


add_subdirectory(${TOPDIR}/coap/src ${BUILDDIR}/coap/src)
add_subdirectory(${TOPDIR}/coap/test ${BUILDDIR}/coap/test)


add_subdirectory(${TOPDIR}/proxy/http_coap/src ${BUILDDIR}/proxy/http_coap/src)