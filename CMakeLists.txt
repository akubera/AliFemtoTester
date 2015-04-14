#
# CMakeLists.txt
#
# CMake build script for AliFemtoTester
#


cmake_minimum_required(VERSION 2.8.11 FATAL_ERROR) # match AliPhysics

project(AliFemtoTester CXX C)

enable_testing()

set(ROOTSYS $ENV{ROOTSYS} CACHE PATH "Path to the ROOT installation")
set(ALIROOT $ENV{ALICE_ROOT} CACHE PATH "Path to the AliROOT installation")
set(ALIPHYSICS $ENV{ALICE_PHYSICS} CACHE PATH "Path to the AliPhysics installation")

set(ROOT_CONFIG FILEPATH ${ROOTSYS}/bin/root-config "The root-config script to help determine build parameters")

#function (CONF_EXE ARG OUTPUT)
#  execute_process(${ROOT_CONFIG} ${ARG} OUTPUT_VARIABLE ${OUTPUT})
#endfunction (CONF_EXE ARG OUTPUT)
#config_exe("--cc" CC)

message(STATUS "CC: ${CC}")

add_subdirectory (tests)
