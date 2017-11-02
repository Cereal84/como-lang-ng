#
# Written by: Alessandro Pischedda <alessandro.pischedda@gmail.com>
#

AC_INIT([como-lang-ng],
        m4_esyscmd([build-aux/git-version-gen --prefix v .tarball-version]),
        [alessandro.pischedda@gmail.com],[como-lang-ng])

AC_PREREQ([2.61])

AC_CONFIG_SRCDIR([src/como.c])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])

AM_INIT_AUTOMAKE([1.10 foreign no-installman no-installinfo subdir-objects -Wall])

AC_PROG_SED
AC_PROG_GREP

AC_PROG_CPP
AC_PROG_CC
AC_PROG_CXXCPP
AC_PROG_CXX
AC_PROG_CXX_C_O

AM_PROG_AR

LT_INIT
LT_PREREQ([2.2.6])

AC_PROG_LN_S


# --with-log-dir option
AC_ARG_WITH([log-dir], [AS_HELP_STRING([--with-log-dir=DIR],[the directory for log files])],[
    ax_log_dir="$withval"
],[
    ax_log_dir="/var/log"
])
AC_SUBST([LOGDIR],[$ax_log_dir])
AC_MSG_NOTICE([Using '$ax_log_dir' as log directory])

AC_CONFIG_FILES([
        Makefile
        src/Makefile
])

AC_OUTPUT
