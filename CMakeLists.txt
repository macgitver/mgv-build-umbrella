
PROJECT( BuildUmbrella )
CMAKE_MINIMUM_REQUIRED( VERSION 2.8.9 )

CMAKE_POLICY( SET CMP0009 NEW )

SET( UTILS_APP_NAME         BuildUmrella CACHE INTERNAL "Foo" )
SET( UTILS_USE_PRIVATE_LIBS 1            CACHE INTERNAL "Foo" )

INCLUDE( cmake/Utils.cmake )
SET_OUTPUT_PATHS()
INCLUDE( cmake/QtMacros.cmake )

IF( UNIX )
    GCC_ADD_FLAG( "-Wall" )
    GCC_ADD_FLAG( "-fvisibility=hidden" )
ENDIF()

FOREACH( dir ${MODS} )
    ADD_SUBDIRECTORY( ${dir} )
ENDFOREACH()
