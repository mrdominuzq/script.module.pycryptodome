cmake_minimum_required(VERSION 2.8)

project(pycryptodome)

include(ExternalProject)

externalproject_add(pycryptodome
  SOURCE_DIR ${CMAKE_SOURCE_DIR}
  CONFIGURE_COMMAND CC=${CMAKE_C_COMPILER} PYTHONPATH=${OUTPUT_DIR} ${NATIVEPREFIX}/bin/python ${CMAKE_SOURCE_DIR}/setup.py build
  INSTALL_COMMAND ""
  BUILD_IN_SOURCE 1)

install(CODE "execute_process(COMMAND PYTHONPATH=${OUTPUT_DIR} ${NATIVEPREFIX}/bin/python setup.py install WORKING_DIRECTORY ${CMAKE_SOURCE_DIR})")
