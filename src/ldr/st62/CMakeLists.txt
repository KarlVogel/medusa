set(INCROOT ${CMAKE_SOURCE_DIR}/src/ldr/st62)
set(SRCROOT ${CMAKE_SOURCE_DIR}/src/ldr/st62)

# all source files
set(SRC
  ${SRCROOT}/main.cpp
  ${SRCROOT}/st62_loader.cpp
  ${INCROOT}/st62_loader.hpp
  )

add_library(ldr_st62 SHARED ${SRC})
target_link_libraries(ldr_st62 Medusa)
set_target_properties(ldr_st62 PROPERTIES FOLDER "Loaders")

if(WIN32)
  install(TARGETS ldr_st62 RUNTIME DESTINATION .)
else()
  install(TARGETS ldr_st62 LIBRARY DESTINATION .)
endif()
