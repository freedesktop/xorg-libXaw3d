SUBDIRS = include src

install-exec-hook:
	cd $(DESTDIR)$(libdir) && rm -f libXaw3d.@LIBEXT@ && $(LN_S) $(DEFAULT_LIB) libXaw3d.@LIBEXT@

uninstall-local:
	-rm -f $(DESTDIR)$(libdir)/libXaw3d.@LIBEXT@
