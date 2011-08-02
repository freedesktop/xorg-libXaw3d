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
	sharedlib.c \
	Simple.c \
	SimpleMenu.c \
	SmeBSB.c \
	Sme.c \
	SmeLine.c \
	SmeThreeD.c \
	StripChart.c \
	Template.c \
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
	XawInit.c

libXaw3d_la_CFLAGS = \
	$(CWARNFLAGS)

libXaw3d_la_CPPFLAGS = \
	-I${top_srcdir}/include \
	-I${top_srcdir}/include/X11/Xaw3d \
	-DPROJECT_ROOT=\"$(prefix)\"

libXaw3d_la_LDFLAGS = -version-info 8:0:0 -no-undefined

if !PLATFORM_WIN32
install-exec-hook::
if PLATFORM_DARWIN
	-rm -f $(DESTDIR)$(libdir)/libXaw3d.8.@LIBEXT@
	(cd $(DESTDIR)$(libdir) && ln -s libXaw3d.8.@LIBEXT@ libXaw3d.8.@LIBEXT@)
else
	-rm -f $(DESTDIR)$(libdir)/libXaw3d.@LIBEXT@.8
	(cd $(DESTDIR)$(libdir) && ln -s libXaw3d.@LIBEXT@.8 libXaw3d.@LIBEXT@.8)
endif

uninstall-local::
if PLATFORM_DARWIN
	-rm -f $(DESTDIR)$(libdir)/libXaw3d.8.@LIBEXT@
else
	-rm -f $(DESTDIR)$(libdir)/libXaw3d.@LIBEXT@.8
endif
endif

EXTRA_DIST = sharedlib.c
