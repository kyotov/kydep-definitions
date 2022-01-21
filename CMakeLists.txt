# ==============================================================================
# ===== [BEGIN] KyDeps CMakeLists.txt preamble ===== !!! DO NOT EDIT !!! =======
#
cmake_minimum_required(VERSION 3.22)
project(kydeps)
include(FetchContent)
FetchContent_Declare(kydep_bootstrap
    GIT_REPOSITORY https://github.com/kyotov/kydep-bootstrap.git
    GIT_TAG v2.4
)
FetchContent_MakeAvailable(kydep_bootstrap)
#
# ===== [END] KyDeps CMakeLists.txt preamble ===================================
# ==============================================================================

IncludeGlob("*.cmake")
