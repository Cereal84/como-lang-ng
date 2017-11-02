#
# Written by: Alessandro Pischedda <alessandro.pischedda@gmail.com>
#

ACLOCAL_AMFLAGS = -I m4
EXTRA_DIST      = bootstrap build-aux/git-version-gen
DISTCLEANFILES  =
BUILT_SOURCES   =
SUBDIRS         = src

EXTRA_DIST      +=  bootstrap                       \
                    build-aux/git-version-gen       \
                    doc                             \
                    support                         \
                    vm                              \
                    test

EXTRA_DIST      += README.md

EXTRA_DIST    += $(top_srcdir)/.version
BUILT_SOURCES += $(top_srcdir)/.version
$(top_srcdir)/.version:
	echo $(VERSION) > $@-t && mv $@-t $@
dist-hook:
	echo $(VERSION) > $(distdir)/.tarball-version

DISTCHECK_CONFIGURE_FLAGS=              \
    --with-spa-archives=/usr/lib/       \
    --enable-client                     \
    --enable-notificationd

include Makefile-gentoo.am
