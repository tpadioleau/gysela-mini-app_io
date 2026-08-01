# SPDX-License-Identifier: MIT

add_executable(gys_io
    gys_io.cpp
    fluid_moments.cpp
)

target_link_libraries(gys_io
    PUBLIC
        DDC::core
        DDC::pdi
        PDI::PDI_C
        paraconf::paraconf
        MPI::MPI_CXX
        gyselalibxx::quadrature
        gyselalibxx::utils
        gyselalibxx::speciesinfo
        gyselalibxx::io
        gyselalibxx::mpi_parallelisation
)

# Set PYTHONPATH to include the python directory for Python module imports
get_filename_component(PROJECT_ROOT_DIR ${CMAKE_SOURCE_DIR} ABSOLUTE)
set(PYTHON_MODULE_PATH "${PROJECT_ROOT_DIR}/src/python")
set_target_properties(gys_io PROPERTIES
    ENVIRONMENT "PYTHONPATH=${PYTHON_MODULE_PATH}:$ENV{PYTHONPATH}"
)

install(TARGETS gys_io)
