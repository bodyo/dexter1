add_executable(dexter
               dexter.cc
               dissasembler.cc
               experimental.cc
               main.cc)

include_directories ("${PROJECT_SOURCE_DIR}/dex")

set(LINK_DEPENDENCIES z)

if(ANDROID)
  set(LINK_DEPENDENCIES ${LINK_DEPENDENCIES}
                        gnustl_static)
endif()

target_link_libraries(dexter slicer ${LINK_DEPENDENCIES})


