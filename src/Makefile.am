#
# Written by:  Alessandro Pischedda <alessandro.pischedda@gmail.com>
#


EXTRA_DIST     =
CLEAN_FILES    =
DISTCLEANFILES =

COMMONCPPFLAGS = -g $(COMPILE_FULL_FLAGS)


bin_PROGRAMS   = como


EXTRA_DIST +=   db_def.h.in   \
                options.cxx.in

CLEAN_FILES +=  db_def.h.in  \
                options.cxx.in

db_def.h: db_def.h.in
	echo "build db def"                          \
	rm -f $@ $@.tmp                              \
	srcdir='';                                   \
	   test -f ./$@.in || srcdir=$(srcdir)/;     \
	   $(edit_db) $${srcdir}$@.in >$@.tmp
	chmod a-w $@.tmp
	mv $@.tmp $@

options.cxx: options.cxx.in
	echo "build db def"                          \
	rm -f $@ $@.tmp                              \
	srcdir='';                                   \
	   test -f ./$@.in || srcdir=$(srcdir)/;     \
	   $(edit_options) $${srcdir}$@.in >$@.tmp
	chmod a-w $@.tmp
	mv $@.tmp $@


alarm_manager.cxx: db_def.h
am_db_utils.hxx: db_def.h


como_SOURCES  =                                                    \
        como.c                                                     \
        como_globals.h                                             \
        como_ast.c                      como_ast.h                 \
        como_ast_free.c                                            \
        como_stack.c                    como_stack.h               \
        como_io.c                       como_io.h                  \
        como_debug.c                    como_debug.h               \
        como_compiler.c                 como_compiler.h            \
        como_lexer.l                    como_lexer.h               \
        como_object.c                   como_object.h              \
        como_opcode.c                   como_opcode.h              \
        como_parser.c                   como_parser.h


como_CFLAGS =			\
	$(COMMONCPPFLAGS)

alarm_manager_LDADD =                           \
    -lobjects

CLEAN_FILES     += como
DISTCLEANFILES  += como
