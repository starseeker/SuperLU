#######################################################################
#  This is the CMakeLists.txt file for building SuperLU's local
#  C-BLAS library. The files are organized as follows:
#
#       SBLAS1 -- Single precision real BLAS routines
#       CBLAS1 -- Single precision complex BLAS routines
#       DBLAS1 -- Double precision real BLAS routines
#       ZBLAS1 -- Double precision complex BLAS routines
#
#       SBLAS2 -- Single precision real BLAS2 routines
#       CBLAS2 -- Single precision complex BLAS2 routines
#       DBLAS2 -- Double precision real BLAS2 routines
#       ZBLAS2 -- Double precision complex BLAS2 routines
#
#######################################################################

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../src)

if(NOT CBLAS_PRECISIONS)
  set(CBLAS_PRECISIONS single double complex complex16)
endif(NOT CBLAS_PRECISIONS)
string(TOUPPER "${CBLAS_PRECISIONS}" CBLAS_PRECISIONS)

set(SBLAS1 isamax.c sasum.c saxpy.c scopy.c sdot.c snrm2.c srot.c sscal.c sswap.c)
set(SBLAS2 sgemv.c ssymv.c strsv.c sger.c ssyr2.c)
set(SINGLE_SRCS ${SBLAS1} ${SBLAS2})

set(DBLAS1 idamax.c dasum.c daxpy.c dcopy.c ddot.c dnrm2.c drot.c dscal.c dswap.c)
set(DBLAS2 dgemv.c dsymv.c dtrsv.c dger.c dsyr2.c)
set(DOUBLE_SRCS ${DBLAS1} ${DBLAS2})

set(CBLAS1 icamax.c scasum.c caxpy.c ccopy.c scnrm2.c cscal.c cswap.c )
set(CBLAS2 cgemv.c chemv.c ctrsv.c cgerc.c cher2.c )
set(COMPLEX_SRCS ${CBLAS1} ${CBLAS2})

set(ZBLAS1 izamax.c dzasum.c zaxpy.c zcopy.c dznrm2.c zscal.c dcabs1.c zswap.c )
set(ZBLAS2 zgemv.c zhemv.c ztrsv.c zgerc.c zher2.c )
set(COMPLEX16_SRCS ${ZBLAS1} ${ZBLAS2})

foreach(precision ${CBLAS_PRECISIONS})
  set(CBLAS_SRCS ${CBLAS_SRCS} ${${precision}_SRCS})
endforeach(precision ${CBLAS_PRECISIONS})

add_library(superlu_cblas ${CBLAS_SRCS})

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
