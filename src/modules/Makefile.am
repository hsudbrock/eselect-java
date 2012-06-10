modulesdir=$(datadir)/eselect/modules/

modules_DATA = \
	ecj.eselect \
	java-nsplugin.eselect \
	java-vm.eselect \
	maven.eselect

EXTRA_DIST = \
	ecj.eselect.in \
	java-nsplugin.eselect.in \
	java-vm.eselect.in \
	maven.eselect.in

CLEANFILES = $(modules_DATA)
MAINTAINERCLEANFILES = Makefile.in

%.eselect : %.eselect.in
	$(SED) "s|\@VERSION\@|@PACKAGE_VERSION@|g" $< >$@
