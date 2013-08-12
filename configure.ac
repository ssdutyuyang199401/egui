#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([egui], [0.1], [stonekyx@gmail.com])
AC_CONFIG_HEADERS([include/config.h])
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE([subdir-objects])
LT_INIT

# Checks for programs.
AC_PROG_AWK
AC_PROG_CC
AC_PROG_LN_S
AC_PROG_MAKE_SET

# Checks for header files.
AC_CHECK_HEADERS([fcntl.h limits.h stddef.h stdlib.h string.h sys/ioctl.h sys/socket.h sys/time.h termios.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_TYPE_PID_T

my_save_cflags="$CFLAGS"
CFLAGS="-std=c99 -pedantic -Wall -g"
AC_MSG_CHECKING([whether CC supports -std=c99 -pedantic -Wall -g])
AC_COMPILE_IFELSE([AC_LANG_PROGRAM([])],
                [AC_MSG_RESULT([yes])]
                [AM_CFLAGS="-std=c99 -pedantic -Wall -g"],
                [AC_MSG_RESULT([no])]
                [AC_MSG_WARN([Your compiler may not support c99, compiling is likely to fail.])]
                )
AC_SUBST([AM_CFLAGS])

CFLAGS="-I/usr/include"
AC_MSG_CHECKING([whether CC supports -I])
AC_COMPILE_IFELSE([AC_LANG_PROGRAM([])],
                [AC_MSG_RESULT([yes])]
                [AM_CPPFLAGS='-I$(top_srcdir)/include'],
                [AC_MSG_RESULT([no])]
                [AC_MSG_WARN([Your compiler may not support -I flag, compiling is very likely to fail.])]
                )
AC_SUBST([AM_CPPFLAGS])
CFLAGS="$my_save_cflags"

# Checks for library functions.
AC_FUNC_FORK
AC_FUNC_LSTAT_FOLLOWS_SLASHED_SYMLINK
AC_FUNC_MALLOC
AC_FUNC_MMAP
AC_CHECK_FUNCS([getcwd memmove memset munmap select socket strchr strerror strstr])

# Substitutions

AC_CONFIG_FILES([Makefile])
#                 application/Makefile
#                 client_lib/Makefile
#                 comm/Makefile
#                 debug/Makefile
#                 debug/comm/Makefile
#                 debug/config_parser/Makefile
#                 debug/event/Makefile
#                 debug/graph/Makefile
#                 debug/lib/Makefile
#                 debug/samples/Makefile
#                 debug/samples/calculator/Makefile
#                 debug/samples/file_browser/Makefile
#                 debug/widget/Makefile
#                 event/Makefile
#                 graph/Makefile
#                 graph/graph_engine/Makefile
#                 graph/graph_lower/Makefile
#                 server_lib/Makefile
#                 utils/Makefile
#                 utils/color/Makefile
#                 utils/config_parser/Makefile
#                 utils/data_structures/Makefile
#                 utils/geometry/Makefile
#                 widget/Makefile
#                 widget/button/Makefile
#                 widget/dialog/Makefile
#                 widget/icon/Makefile
#                 widget/image_view/Makefile
#                 widget/label/Makefile
#                 widget/message_box/Makefile
#                 widget/panel/Makefile
#                 widget/scroll_bar/Makefile
#                 widget/text_line/Makefile
#                 widget/widget/Makefile
#                 widget/window/Makefile
#                 window_manager/Makefile])
AC_OUTPUT