
project(netcfgplugin)

set(SOURCES
src/netcfgplugin.cpp 
)

add_library (netcfgplugin MODULE ${SOURCES})

target_link_libraries(netcfgplugin utils far2l)

target_compile_definitions(netcfgplugin PRIVATE -DWINPORT_DIRECT -DUNICODE -DFAR_DONT_USE_INTERNALS)

target_include_directories(netcfgplugin PRIVATE .)
target_include_directories(netcfgplugin PRIVATE ${CMAKE_SOURCE_DIR}/WinPort)
target_include_directories(netcfgplugin PRIVATE ${CMAKE_SOURCE_DIR}/far2l/far2sdk)

set_target_properties(netcfgplugin
    PROPERTIES
        LIBRARY_OUTPUT_DIRECTORY "${INSTALL_DIR}/Plugins/netcfgplugin/plug"
        PREFIX ""
        SUFFIX ".far-plug-wide")
