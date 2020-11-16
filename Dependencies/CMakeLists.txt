include(FetchContent)

if(UNIX)
    find_package(PkgConfig)
    pkg_check_modules(CAPSTONE REQUIRED capstone)
    pkg_check_modules(KEYSTONE REQUIRED keystone)
endif()

if(NOT ${CAPSTONE_FOUND})
    add_subdirectory(capstone)
endif()

if(NOT ${KEYSTONE_FOUND})
    add_subdirectory(keystone)
endif()
