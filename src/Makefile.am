lib_LTLIBRARIES = libXaw3d.la

#
# This doesn't appear to be used on any
# current systems -- it requires SUNSHLIB and !SHAREDCODE,
# but only sunLib.rules defines SUNSHLIB and that file also
# always defines SHAREDCODE. Go figure
#
# SHAREDLIB_SOURCES = sharedlib.c

libXaw3d_la_SOURCES = \
	AllWidgets.c \
	AsciiSink.c \
	AsciiSrc.c \
	AsciiText.c \
	Box.c \
	Command.c \
	Dialog.c \
	Form.c \
	Grip.c \
	Label.c \
	Layout.c \
	List.c \
	MenuButton.c \
	MultiSink.c \
	MultiSrc.c \
	Paned.c \
	Panner.c \
	Porthole.c \
	Repeater.c \
	Scrollbar.c \
	Simple.c \
	SimpleMenu.c \
	SmeBSB.c \
	Sme.c \
	SmeLine.c \
	SmeThreeD.c \
	StripChart.c \
	TextAction.c \
	Text.c \
	TextPop.c \
	TextSink.c \
	TextSrc.c \
	TextTr.c \
	ThreeD.c \
	Tip.c \
	Toggle.c \
	Tree.c \
	Vendor.c \
	Viewport.c \
	Xaw3dP.c \
	XawI18n.c \
	XawIm.c \
	XawInit.c \
	laygram.y \
	laylex.l

libXaw3d_la_CFLAGS = \
	$(CWARNFLAGS) $(X11_CFLAGS)

libXaw3d_la_LIBADD = \
	$(X11_LIBS)

libXaw3d_la_CPPFLAGS = \
	-I${top_srcdir}/include \
	-I${top_srcdir}/include/X11/Xaw3d \
	-DPROJECT_ROOT=\"$(prefix)\"

libXaw3d_la_LDFLAGS = -version-info 8:0:0 -no-undefined

EXTRA_DIST = sharedlib.c Template.c
