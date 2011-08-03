
# Initialize Autoconf
AC_PREREQ([2.60])
AC_INIT([libXaw3d], [1.5E])
AC_CONFIG_SRCDIR([Makefile.am])

# Initialize Automake
AM_INIT_AUTOMAKE([foreign dist-bzip2])
AM_MAINTAINER_MODE
AC_PROG_LEX
AC_PROG_YACC

# Initialize libtool
AC_PROG_LIBTOOL

# Some compilers do not support per target -c and -o flags
AM_PROG_CC_C_O

# Checks for programs.

# Need to call this explicitly since the first call to PKG_CHECK_MODULES
# is in an if statement, and later calls would break if it's skipped.
PKG_PROG_PKG_CONFIG

# Checks for header files.
PKG_CHECK_MODULES(X11, [x11 xt xmu])
AC_CHECK_HEADERS([wctype.h wchar.h widec.h])

AC_CONFIG_FILES([Makefile
		include/Makefile
		src/Makefile])

AC_OUTPUT
