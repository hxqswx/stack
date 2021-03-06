#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_INIT([stack],[0.3],[int@pdos.csail.mit.edu])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_HEADERS([config.h])

AM_INIT_AUTOMAKE([foreign -Wall -Werror])
m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])])

# Checks for programs.
AM_PROG_CC_C_O
AC_PROG_CXX
m4_ifdef([AM_PROG_AR],[AM_PROG_AR])
AC_PROG_LN_S
AC_PROG_MKDIR_P
AC_PROG_SED

LT_INIT([disable-static pic-only])
AC_PROG_LIBTOOL

# Checks for timer
AC_SEARCH_LIBS(
	[timer_create],[rt],
	AC_DEFINE([HAVE_TIMER],[1],[Define to 1 if you have the per-process timer.])
)

AC_CONFIG_FILES([
	Makefile
	lib/Makefile
	src/Makefile
	test/Makefile
	test/lit.cfg
])
AC_CONFIG_LINKS([
	bin/stack/gcc:test/gcc
	bin/stack/g++:test/gcc
	bin/stack/cc:test/gcc
	bin/stack/c++:test/gcc
	bin/stack/cc1:test/cc1
	bin/stack/clang:test/gcc
	bin/stack/clang++:test/gcc
	bin/stack/arm-linux-gnueabi-gcc:test/arm-linux-gnueabi-gcc
	bin/stack/arm-linux-gnueabi-g++:test/arm-linux-gnueabi-g++
	bin/stack-build:test/stack-build
	bin/ncpu:src/ncpu
	bin/optck:src/optck
	bin/poptck:src/poptck
])
AC_OUTPUT
