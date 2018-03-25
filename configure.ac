#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT(algorithm, 1.0)
AC_CONFIG_SRCDIR([src/bubbleSort/bubble.cc])
AC_CONFIG_HEADERS([config.h])

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC

# Checks for libraries.

# Checks for header files.
AC_CHECK_HEADERS([stdlib.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL

# Checks for library functions.
AC_FUNC_MALLOC

AM_INIT_AUTOMAKE
AC_CONFIG_FILES([Makefile
src/bubbleSort/Makefile  
src/heapSort/Makefile  
src/mergeSort/Makefile  
src/quickSort/Makefile])



AC_OUTPUT
