cmake_minimum_required(VERSION 3.10)

# Here you can set your VMOD name
# A unique VMOD name will allow your VMOD to live among other
# VMODs in a larger build system, as well as automatically set
# the appropriate output filename.
# For "example" the output will be "libvmod_example.so".
set(VMOD_NAME example)

project(vmod_${VMOD_NAME} VERSION 0.0.1)

include(vmod.cmake)

vmod(${VMOD_NAME} 6.6 src/vmod_${VMOD_NAME}.c)

file(GLOB vtc_paths ${CMAKE_CURRENT_SOURCE_DIR}/tests/*.vtc)
vtc(${VMOD_NAME} "${vtc_paths}")
