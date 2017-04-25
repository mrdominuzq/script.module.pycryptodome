project(script.module.pycryptodome)

cmake_minimum_required(VERSION 2.6)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${PROJECT_SOURCE_DIR})

enable_language(CXX)

find_package(PkgConfig)
find_package(Kodi REQUIRED)
find_package(PYCRYPTODOME REQUIRED)

include_directories(${INCLUDES}
                    ${PYCRYPTODOME_INCLUDE_DIRS}
                    ${KODI_INCLUDE_DIR})
                    
list(APPEND DEPLIBS ${PYCRYPTODOME_LIBRARIES})

build_addon(script.module.pycryptodome PYCRYPTODOME DEPLIBS)

include(CPack)
