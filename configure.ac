
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

# Require xorg-macros minimum of 1.8 for XORG_DEFAULT_OPTIONS with XORG_INSTALL
m4_ifndef([XORG_MACROS_VERSION],
          [m4_fatal([must install xorg-macros 1.8 or later before running autoconf/autogen])])
XORG_MACROS_VERSION(1.8)
XORG_DEFAULT_OPTIONS

# Some compilers do not support per target -c and -o flags
AM_PROG_CC_C_O

# Checks for header files.
PKG_CHECK_MODULES(X11, [x11 xt xmu])
AC_CHECK_HEADERS([wctype.h wchar.h widec.h])
AC_CHECK_FUNCS([iswspace])

XAW3D_CFLAGS=

AC_ARG_ENABLE([internationalization],
    [AS_HELP_STRING([--enable-internationalization], dnl
     [enable utf8 strings])], [XAW3D_CFLAGS="${XAW3D_CFLAGS} -DXAW_INTERNATIONALIZATION"])

AM_CONDITIONAL(XAW_INTERNATIONALIZATION,
    [test x${enable_internationalization} = xyes])

AC_ARG_ENABLE([multiplane-bitmaps],
    [AS_HELP_STRING([--enable-multiplane-bitmaps], dnl
     [enable XPM support])],
     [XAW3D_CFLAGS="${XAW3D_CFLAGS} -DXAW_MULTIPLANE_PIXMAPS" dnl
      PKG_CHECK_MODULES(XPM, xpm)])

AC_ARG_ENABLE([gray-stipples],
    [AS_HELP_STRING([--enable-gray-stipples], dnl
     [enable gray stipples])], [XAW3D_CFLAGS="${XAW3D_CFLAGS} -DXAW_GRAY_BLKWHT_STIPPLES"])

AC_ARG_ENABLE([arrow-scrollbars],
    [AS_HELP_STRING([--enable-arrow-scrollbars], dnl
     [enable arrow scrollbars])], [XAW3D_CFLAGS="${XAW3D_CFLAGS} -DXAW_ARROW_SCROLLBARS"])

AC_SUBST(XAW3D_CFLAGS)

AC_CONFIG_FILES([Makefile
		include/Makefile
		src/Makefile
		xaw3d.pc])

AC_OUTPUT
