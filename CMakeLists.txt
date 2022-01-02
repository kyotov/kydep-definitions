# ==============================================================================
# ===== [BEGIN] KyDeps CMakeLists.txt preamble ===== !!! DO NOT EDIT !!! =======
#
cmake_minimum_required(VERSION 3.20)
project(kydeps)

set(DEPS_SOURCE_DIR "${CMAKE_CURRENT_SOURCE_DIR}")
if (NOT (CMAKE_SOURCE_DIR STREQUAL DEPS_SOURCE_DIR))
    include(FetchContent)
    FetchContent_Declare(kydep_bootstrap
        GIT_REPOSITORY https://github.com/kyotov/kydep-bootstrap.git
        GIT_TAG v1.0
    )
    FetchContent_MakeAvailable(kydep_bootstrap)
    set(CMAKE_PREFIX_PATH "${CMAKE_PREFIX_PATH}" PARENT_SCOPE)
    return()
endif()

include(kydep)
#
# ===== [END] KyDeps CMakeLists.txt preamble ===================================
# ==============================================================================

# TODO(kamen): consider populating ${KYDEPS} if empty
foreach(KYDEP ${KYDEPS})
    include("${KYDEP}.cmake")
endforeach()
