SUBDIRS = src/modules

MAINTAINERCLEANFILES = \
	aclocal.m4 \
	install-sh \
	missing \
	configure \
	Makefile.in \
	INSTALL

EXTRA_DIST = \
	ChangeLog.old.eselect-ecj \
	ChangeLog.old.eselect-java-nsplugin \
	ChangeLog.old.eselect-java-vm \
	ChangeLog.old.eselect-maven \
	COPYING \
	NEWS \
	README

dist-hook:
	if test -d "$(srcdir)"/.svn ; then \
		echo "Generating ChangeLog ..." ; \
		( cd "$(top_srcdir)" && svn2cl --authors AUTHORS -o "$(top_distdir)"/ChangeLog ) ; \
	else \
		echo "Needs a svn checkout to generate a ChangeLog" ; \
	fi
