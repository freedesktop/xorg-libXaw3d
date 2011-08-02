
# Initialize Autoconf
AC_PREREQ([2.60])
AC_INIT([libXaw3d], [1.5E])
AC_CONFIG_SRCDIR([Makefile.am])

# Initialize Automake
AM_INIT_AUTOMAKE([foreign dist-bzip2])
AM_MAINTAINER_MODE

# Initialize libtool
AC_PROG_LIBTOOL

# Some compilers do not support per target -c and -o flags
AM_PROG_CC_C_O

# Checks for programs.

# Need to call this explicitly since the first call to PKG_CHECK_MODULES
# is in an if statement, and later calls would break if it's skipped.
PKG_PROG_PKG_CONFIG

#
# fix libtool to set SONAME to libXaw3d.so.$major
#
AC_CONFIG_COMMANDS([libtool_hack], [
	cp -f libtool libtool_
	test -z "$SED" && SED=sed
	$SED '1,/^soname_spec/{
/^soname_spec/i\
# X.Org hack to match monolithic Xaw SONAME\
xorglibxawname="libXaw3d"
/^soname_spec/s/libname/xorglibxawname/
}' libtool_ > libtool
	rm -f libtool_
])

# OSX/Win32 rules are different.
platform_win32=no
platform_darwin=no
LIBEXT=so
case $host_os in
    cygwin*|mingw*)
	LIBEXT=dll.a
	platform_win32=yes
	;;
    darwin*)
	LIBEXT=dylib
	platform_darwin=yes
	;;
esac
AC_SUBST(LIBEXT)
AM_CONDITIONAL(PLATFORM_WIN32, test "x$platform_win32" = "xyes")
AM_CONDITIONAL(PLATFORM_DARWIN, test "x$platform_darwin" = "xyes")

# Checks for header files.
AC_CHECK_HEADERS([wctype.h wchar.h widec.h])

AC_CONFIG_FILES([Makefile
		include/Makefile
		src/Makefile])

AC_OUTPUT
