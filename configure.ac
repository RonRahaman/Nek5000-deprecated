AC_INIT([Nek5000],[x.x])
AC_CONFIG_MACRO_DIR([config])

# ---- FROM MAKENEK ----
AC_ARG_VAR([CC], [The C compiler])
AC_ARG_VAR([F77], [The Fortran 77 compiler])


# ---- FROM MAKENEK.INC ----
PPLIST=""
AC_ARG_ENABLE([timer],
              [AS_HELP_STRING([--disable-timer], [disable runtime statistics])],
              [AS_IF([test "x$enableval" != "xno"], [], [PPLIST="${PPLIST} NOTIMER"])])

AC_ARG_ENABLE([mpi-timer],
              [AS_HELP_STRING([--enable-mpi-timer], [enable MPI runtime statistics])],
              [AS_IF([test "x$enableval" != "xno"], [PPLIST="${PPLIST} MPITIMER"])])

AC_ARG_ENABLE([mpi-io],
              [AS_HELP_STRING([--enable-mpi-io], [use MPI-IO i/O kernel (experimental)])],
              [AS_IF([test "x$enableval" != "xno"], [PPLIST="${PPLIST} MPIIO"])])

AC_ARG_ENABLE([bg],
              [AS_HELP_STRING([--enable-bg], [enable Blue Gene optimizations (BG/L and BG/P)])],
              [AS_IF([test "x$enableval" != "xno"], [PPLIST="${PPLIST} BG"])])

AC_ARG_WITH([k10-mxm],
              [AS_HELP_STRING([--with-k10-mxm], [use optimized MxM kernel for AMD Family 10h processors])],
              [AS_IF([test "x$withval" != "xno"], [PPLIST="${PPLIST} K10_MXM"])])

AC_ARG_WITH([cvode],
              [AS_HELP_STRING([--with-cvode], [use ODE solver from Sundials to solve for IFIELD>1 (experimental)])],
              [AS_IF([test "x$withval" != "xno"], [PPLIST="${PPLIST} CVODE"])])
AC_ARG_VAR([CVODE_DIR], [Path to CVODE installation])

AC_ARG_WITH([moab],
              [AS_HELP_STRING([--with-moab], [enable MOAB/CUBIT support (experimental)])],
              [AS_IF([test "x$withval" != "xno"], [PPLIST="${PPLIST} MOAB"])])
AC_ARG_VAR([MOAB_DIR], [Path to MOAB installation])

AC_ARG_ENABLE([neknek],
              [AS_HELP_STRING([--enable-neknek], [enable multidomain support (experimental)])],
              [AS_IF([test "x$enableval" != "xno"], [PPLIST="${PPLIST} NEKNEK"])])

AC_ARG_ENABLE([lapack],
              [AS_HELP_STRING([--disable-lapack], [disable nek-supplied LAPACK routines])],
              [AS_IF([test "x$enableval" != "xno"], [], [PPLIST="${PPLIST} NO_LAPACK"])])

AC_ARG_ENABLE([blas_mxm],
              [AS_HELP_STRING([--disable-blas-mxm], [disable nek-supplied BLAS routines])],
              [AS_IF([test "x$enableval" != "xno"], [], [PPLIST="${PPLIST} BLAS_MXM"])])

AC_ARG_ENABLE([neknek],
              [AS_HELP_STRING([--enable-extbar], [adds underscore to exit call(for BGQ)])],
              [AS_IF([test "x$enableval" != "xno"], [PPLIST="${PPLIST} EXTBAR"])])

# Check makenek version

# Check nocompile option

# Set CASENAME, CASEDIR, APATH_SRC, SOURCE_ROOT, IFMOAB, IFNEKNEK

# Check if out-of-source

# Check for .usr

# Check for SIZE

# Test F77 (missing some from makenek.inc)
#AC_PROG_F77([gfortran pgf77 ifort xlf77])
#AC_PROG_F77_MPI()
AC_PROG_FC([gfortran pgf90 ifort], [Fortran 77])
#AC_PROG_FC_MPI()

# Test CC (missing some from makenek.inc)
AC_PROG_CC([gcc pgcc icc xlcc])
#AC_PROG_CC_MPI()

# Clean executable, subuser.o

# Check CC ptr size.  Defines SIZEOF_INT_P
AC_LANG([C])
AC_CHECK_SIZEOF([int *])

# Check if F77 adds underscore to external functions (name-mangling scheme?)

# Check which F77 and set compiler-specific flags
## Discover cpp flag
AC_FC_PP_SRCEXT([f])

# Set preprocessor symbols...

## Check CC long int size

## Add user-defined preprocessor symbols

# AMG setup

# MxM-handling

# Set opt flags

# Set usr lib

# Generate makefile...

## Handle Visit

## Handle USR

## Handle case

## Add plug-ins

# Generate SIZE file

# Generate .usr file

AC_OUTPUT
