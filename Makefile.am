dist_pkglibexec_SCRIPTS= \
	src/scripts/run-java-tool.bash

EXTRA_DIST = \
	src/scripts/run-java-tool.bash.in

modulesdir=$(datadir)/eselect/modules/

modules_DATA = \
	src/modules/ecj.eselect \
	src/modules/java-vm.eselect \
	src/modules/maven.eselect

EXTRA_DIST += \
	src/modules/ecj.eselect.in \
	src/modules/java-vm.eselect.in \
	src/modules/maven.eselect.in

CLEANFILES = $(dist_pkglibexec_SCRIPTS) $(modules_DATA)

MAINTAINERCLEANFILES = \
	aclocal.m4 \
	install-sh \
	missing \
	configure \
	Makefile.in \
	INSTALL

EXTRA_DIST += \
	ChangeLog \
	ChangeLog.old.eselect-ecj \
	ChangeLog.old.eselect-java-nsplugin \
	ChangeLog.old.eselect-java-vm \
	ChangeLog.old.eselect-maven \
	COPYING \
	NEWS \
	README


create-scripts-dir:
	$(MKDIR_P) $(top_builddir)/src/scripts

$(dist_pkglibexec_SCRIPTS): | create-scripts-dir
	$(SED) "s|\@GENTOO_PORTAGE_EPREFIX\@|@EPREFIX@|g" $(top_srcdir)/$@.in >$@

create-modules-dir:
	$(MKDIR_P) $(top_builddir)/src/modules

$(modules_DATA): | create-modules-dir
	$(SED) "s|\@VERSION\@|@PACKAGE_VERSION@|g" $(top_srcdir)/$@.in >$@

#------------------------------------------------------------------------------
# FIXME let eselect java-vm handle symlinks.
tools = \
	appletviewer \
	apt \
	ControlPanel \
	extcheck \
	HtmlConverter \
	idlj \
	jar \
	jarsigner \
	java \
	javac \
	javadoc \
	javah \
	javap \
	javaws \
	jconsole \
	jcontrol \
	jdb \
	jhat \
	jinfo \
	jmap \
	jps \
	jrunscript \
	jsadebugd \
	jstack \
	jstat \
	jstatd \
	jvisualvm \
	keytool \
	native2ascii \
	orbd \
	pack200 \
	policytool \
	rmic \
	rmid \
	rmiregistry \
	schemagen \
	serialver \
	servertool \
	tnameserv \
	wsgen \
	wsimport \
	xjc

.PHONY: $(tools)

$(tools):
	$(MKDIR_P) "$(DESTDIR)/$(bindir)"
	$(LN_S) $(pkglibexecdir)/run-java-tool.bash "$(DESTDIR)/$(bindir)/$@"

install-exec-hook: $(tools)

