# SPDX-License-Identifier: MIT

cmake_minimum_required(VERSION 3.25)
project(gysela-mini-app_io LANGUAGES CXX)

###############################################################################################
#                              Build libraries and executables
###############################################################################################

## Link to Gyselalibxx++ library
find_package(gyselalibxx REQUIRED)

## Build the simulations (applications mains) in `apps/`
add_subdirectory(apps/)
