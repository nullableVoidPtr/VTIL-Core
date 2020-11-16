include(FetchContent)

if(UNIX)
    find_package(PkgConfig)
    pkg_check_modules(CAPSTONE REQUIRED capstone)
endif()

if(NOT ${CAPSTONE_FOUND})
    add_subdirectory(capstone)
endif()

add_subdirectory(keystone)
