# SuperLU (version 5.0) #
SuperLU contains a set of subroutines to solve a sparse linear system A*X=B. It uses Gaussian elimination with partial pivoting (GEPP). The columns of A may be preordered before factorization; the preordering for sparsity is completely separate from the factorization.

SuperLU is implemented in ANSI C, and must be compiled with standard ANSI C compilers. It provides functionality for both real and complex matrices, in both single and double precision. 
- File names for the single-precision real version start with letter "s" (such as sgstrf.c)
- File names for the double-precision real version start with letter "d" (such as dgstrf.c)
- File names for the single-precision complex version start with letter "c" (such as cgstrf.c)
- File names for the double-precision complex version start with letter "z" (such as zgstrf.c)

Official Homepage: http://crd.lbl.gov/~xiaoye/SuperLU/

## Contents ##

SuperLU contains the following directory structure:

    SuperLU/README.md    Overview and general information
    SuperLU/COPYING.md   License information
    SuperLU/cblas/       Needed BLAS routines in C (not necessarily fast)
    SuperLU/doc/         Users' Guide and documentation of source code
    SuperLU/example/     Example programs
    SuperLU/src/         C source code, to be compiled into the superlu.a library
    SuperLU/testing/     Driver routines to test correctness

Official [Code Documentation](http://crd-legacy.lbl.gov/~xiaoye/SuperLU/superlu_code_html/).

## Releases ##

    Version 1.0 - February 4, 1997
    Version 1.1 - November 15, 1997
    Version 2.0 - September 1, 1999
    Version 3.0 - October 15, 2003
    Version 3.1 - August 1, 2008
    Version 4.0 - June 30, 2009
    Version 4.1 - November 23, 2010
    Version 4.2 - August 25, 2011
    Version 4.3 - October 27, 2011
	Version 5.0 - July 26, 2015

Official [Changelog](http://crd-legacy.lbl.gov/~xiaoye/SuperLU/changes.html#slu_change).
