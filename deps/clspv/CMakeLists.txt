########################################################################################################################
# Copyright (c) 2022-2022 Daemyung Jang.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
########################################################################################################################

cmake_minimum_required(VERSION 3.18)
project(clspv CXX)

add_library(clspv INTERFACE
        include/clspv/AddressSpace.h
        include/clspv/ArgKind.h
        include/clspv/Compiler.h
        include/clspv/Option.h
        include/clspv/Passes.h
        include/clspv/PushConstant.h
        include/clspv/Sampler.h
        include/clspv/SpecConstant.h
)

target_include_directories(clspv
    INTERFACE
        include
)

target_link_directories(clspv
    INTERFACE
        lib
)

target_link_libraries(clspv
    INTERFACE
        libcurses.a
        libz.a
        libclspv_core.a
)
