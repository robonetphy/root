############################################################################
# CMakeLists.txt file for building ROOT graf2d/primitives package
# @author Pere Mato, CERN
############################################################################


ROOT_GLOB_HEADERS(GPrim_v7_dict_headers ${CMAKE_CURRENT_SOURCE_DIR}/v7/inc/ROOT/T*.hxx)
ROOT_GLOB_SOURCES(src RELATIVE ${CMAKE_CURRENT_SOURCE_DIR} v7/src/*.cxx)
ROOT_STANDARD_LIBRARY_PACKAGE(ROOTGraphicsPrimitives
                              HEADERS ${GPrim_v7_dict_headers}
                              SOURCES ${src}
                              DICTIONARY_OPTIONS "-writeEmptyRootPCM"
                              DEPENDENCIES RIO Core)
if(testing)
    add_subdirectory(v7/test)
endif()
