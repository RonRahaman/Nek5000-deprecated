AC_INIT([Nek5000],[x.x])
#AC_CONFIG_MACRO_DIR([config])
m4_include([config/fortran_backport.m4])

# ---- FROM MAKENEK ----
AC_ARG_VAR([CC], [The C compiler])
AC_ARG_VAR([F77], [The Fortran 77 compiler])
AC_ARG_ENABLE([mpi],   
              [AS_HELP_STRING([--enable-mpi], [enable MPI (default: yes)])],
              [], [$enable_mpi="yes"])
AC_ARG_ENABLE([cmt],   
              [AS_HELP_STRING([--enable-cmt], [enable CMT (default: yes)])],
              [], [$enable_cmt="yes"])
AC_ARG_ENABLE([amg],   
              [AS_HELP_STRING([--enable-amg], [enable CMT instead of XXT (default: no)])],
              [], [$enable_amg="no"])
AC_ARG_ENABLE([amg-dump],   
              [AS_HELP_STRING([--enable-amg-dump], [(default: no)])],
              [], [$enable_amg_dump="no"])
AC_ARG_ENABLE([visit], 
              [AS_HELP_STRING([--enable-visit], [enable VisIt in situ (default: no)])],
              [], [$enable_visit="no"])
AC_ARG_ENABLE([visit-stop], 
              [AS_HELP_STRING([--enable-visit-stop], [If using VisIt, stop after first step and wait for visit to connect (default: no)])],
              [], [$enable_visit_stop="no"])
AC_ARG_VAR([VISIT_INSTALL])
AC_ARG_VAR([VISIT_LIB])
AC_ARG_VAR([VISIT_INC])

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

AC_ARG_ENABLE([extbar],
              [AS_HELP_STRING([--enable-extbar], [adds underscore to exit call(for BGQ)])],
              [AS_IF([test "x$enableval" != "xno"], [PPLIST="${PPLIST} EXTBAR"])])

# Check makenek version

# There are some useful Autoconf 2.69 macros (AC_FC_SRCEXT, AC_FC_PP_SRCEXT, 
# AC_FC_PP_DEFINE) that can check $FC for Fortran 77 features.  However, 
# equivalents macros are not provided to check $F77.  Therefore, for the 
# remainder of the script, $FC will be set to $F77. At the end, $F77 will 
# be set to $FC and $FC will be set to its original value.
USER_FC="${FC}"
FC="${F77}"

# Test F77 compiler
AC_PROG_FC([],[Fortran 77])

# Test C compiler
AC_PROG_CC()

# Clean executable, subuser.o

# Check CC ptr size.  Defines SIZEOF_INT_P
AC_LANG([C])
AC_CHECK_SIZEOF([int *])

# Check if F77 adds underscore to external functions (name-mangling scheme?)

# Check which F77 and set compiler-specific flags
## Discover PP extension
#AX_PROG_FC_MPI()
AC_FC_SRCEXT([f77])
AC_FC_PP_SRCEXT([f77])
AC_FC_PP_DEFINE()

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

F77="${FC}"
FC="${USER_FC}"

AC_OUTPUT
