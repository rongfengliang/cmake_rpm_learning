cmake_minimum_required(VERSION 2.8)

project(dalong)

set(CPACK_GENERATOR "RPM")
set(CPACK_PACKAGE_NAME "dalong")
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "Simple CPack demo")
set(CPACK_PACKAGE_VENDOR "dalong")
set(CPACK_PACKAGE_VERSION "1.0.0")
set(CPACK_PACKAGE_VERSION_MAJOR "1")
set(CPACK_PACKAGE_VERSION_MINOR "0")
set(CPACK_PACKAGE_VERSION_PATCH "0")
set(CPACK_RPM_PACKAGE_GROUP "dalong")
set(CPACK_PACKAGE_RELEASE 1)
set(CPACK_RPM_PACKAGE_LICENSE "Apache Licence")

include(CPack)

add_executable(dalong main.c)

add_library(dalongmyadd add.c)

set_target_properties(dalongmyadd PROPERTIES OUTPUT_NAME myadd)

target_link_libraries(dalong dalongmyadd)

target_include_directories(dalong PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

install(TARGETS dalong DESTINATION bin)


