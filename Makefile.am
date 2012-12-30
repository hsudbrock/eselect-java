modulesdir=$(datadir)/eselect/modules/

modules_DATA = \
	src/modules/ecj.eselect \
	src/modules/java-nsplugin.eselect \
	src/modules/java-vm.eselect \
	src/modules/maven.eselect

EXTRA_DIST = \
	src/modules/ecj.eselect.in \
	src/modules/java-nsplugin.eselect.in \
	src/modules/java-vm.eselect.in \
	src/modules/maven.eselect.in

CLEANFILES = $(modules_DATA)

MAINTAINERCLEANFILES = \
	aclocal.m4 \
	install-sh \
	missing \
	configure \
	Makefile.in \
	INSTALL

EXTRA_DIST += \
	ChangeLog.old.eselect-ecj \
	ChangeLog.old.eselect-java-nsplugin \
	ChangeLog.old.eselect-java-vm \
	ChangeLog.old.eselect-maven \
	COPYING \
	NEWS \
	README


create-modules-dir:
	$(MKDIR_P) $(top_builddir)/src/modules

$(modules_DATA): | create-modules-dir
	$(SED) "s|\@VERSION\@|@PACKAGE_VERSION@|g" $(top_srcdir)/$@.in >$@

dist-hook:
	if test -d "$(srcdir)"/.svn ; then \
		echo "Generating ChangeLog ..." ; \
		( cd "$(top_srcdir)" && svn2cl --authors AUTHORS -o "$(top_distdir)"/ChangeLog ) ; \
	else \
		echo "Needs a svn checkout to generate a ChangeLog" ; \
	fi
