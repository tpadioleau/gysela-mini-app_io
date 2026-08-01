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

install(TARGETS gys_io)
