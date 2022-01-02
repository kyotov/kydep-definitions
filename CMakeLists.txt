# ==============================================================================
# ===== [BEGIN] KyDeps CMakeLists.txt preamble ===== !!! DO NOT EDIT !!! =======
#
cmake_minimum_required(VERSION 3.20)
project(kydeps)
if (CMAKE_SOURCE_DIR STREQUAL kydeps_SOURCE_DIR)
    include(kydep)
else()
    include(FetchContent)
    FetchContent_Declare(kydep_bootstrap
        GIT_REPOSITORY https://github.com/kyotov/kydep-bootstrap.git
        GIT_TAG v2
    )
    FetchContent_MakeAvailable(kydep_bootstrap)
endif()
#
# ===== [END] KyDeps CMakeLists.txt preamble ===================================
# ==============================================================================

foreach(KYDEP glog gflags GTest)
    include("${KYDEP}.cmake")
endforeach()
