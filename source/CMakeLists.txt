set( CMAKE_CXX_STANDARD 17 )
set( CMAKE_CXX_STANDARD_REQUIRED ON )
set( CMAKE_CXX_EXTENSIONS OFF )

add_library( ${SON8_LIB} INTERFACE )

# son8 libraries
# -- c_header
if( NOT TARGET son8__c_header )
    include( FetchContent )
    message( STATUS "${SON8_LIB}: FetchContent `soneight/c_header`" )
    fetchcontent_declare(
        son8__c_header
        GIT_REPOSITORY https://github.com/soneight/c_header.git
        GIT_TAG        d7e6e7188101d4af0738a6b3a67d47c180d8c559 # v0.1.1
    )
    fetchcontent_makeavailable( son8__c_header )
endif( )
message( STATUS "${SON8_LIB}: found `son8__c_header` target" )
# -- cxx_unit
if( NOT TARGET son8__cxx_unit )
    include( FetchContent )
    message( STATUS "${SON8_LIB}: FetchContent `soneight/cxx_unit`" )
    fetchcontent_declare(
        son8__cxx_unit
        GIT_REPOSITORY https://github.com/soneight/cxx_unit.git
        GIT_TAG        cfdeca7f25de2c1e55e28fc629d7961a0e87d625 # v0.0.1
    )
    fetchcontent_makeavailable( son8__cxx_unit )
endif( )
message( STATUS "${SON8_LIB}: found `son8__cxx_unit` target" )

# Apache License 2.0
# NO WARRANTY OF ANY KIND see <http://www.apache.org/licenses/LICENSE-2.0>
# SPDX-License-Identifier: Apache-2.0
# lib: `core_lib` C++17 Core Library
# Ⓒ Copyright (c) 2026 Oleg'Ease'Kharchuk ᦒ
