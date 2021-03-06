# Generated automatically from Makefile.in by configure.
# Makefile.in generated automatically by automake from Makefile.am.
# Copyright (C) 1994 Free Software Foundation, Inc.

# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2, or (at your option)
# any later version.

# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.

# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 675 Mass Ave, Cambridge, MA 02139, USA.

SHELL = /bin/sh

srcdir = .
top_srcdir = ..
prefix = /usr/local
exec_prefix = ${prefix}

bindir = $(exec_prefix)/bin
sbindir = $(exec_prefix)/sbin
libexecdir = $(exec_prefix)/libexec
datadir = $(prefix)/share
sysconfdir = $(prefix)/etc
sharedstatedir = $(prefix)/com
localstatedir = $(prefix)/var
libdir = $(exec_prefix)/lib
infodir = $(prefix)/info
mandir = $(prefix)/man
includedir = $(prefix)/include
oldincludedir = /usr/include

INSTALL = /usr/bin/ginstall -c
INSTALL_PROGRAM = ${INSTALL}
INSTALL_DATA = ${INSTALL} -m 644
transform = s,x,x,

ALL = ${PROGRAMS} ${LIBPROGRAMS} ${SCRIPTS} ${LIBSCRIPTS} ${LIBFILES}
CC = gcc
LEX = @LEX@
YACC = @YACC@
ANSI2KNR = ./ansi2knr

DEFS = -DHAVE_CONFIG_H
CPPFLAGS = 
CFLAGS = -g -O
LDFLAGS = 
LIBS = 

locate_SOURCES = locate.c
locate_OBJECTS = locate.o
frcode_SOURCES = frcode.c
frcode_OBJECTS = frcode.o
code_SOURCES = code.c
code_OBJECTS = code.o
bigram_SOURCES = bigram.c
bigram_OBJECTS = bigram.o
NROFF = nroff

SOURCES =  locate.c frcode.c code.c bigram.c
DIST_CONF = Makefile.am Makefile.in
DIST_FILES = $(DIST_CONF) $(SOURCES) $(TEXINFOS) $(INFOS) $(MANS) $(DIST_OTHER)

# The default database to build and search.
LOCATE_DB = $(localstatedir)/locatedb

PROGRAMS = locate
LIBPROGRAMS = frcode code bigram
SCRIPTS = updatedb
MANS = locate.1 updatedb.1 locatedb.5
CONFIG_HEADER = ../config.h

DIST_OTHER = locatedb.h updatedb.sh
CLEANFILES = updatedb

INCLUDES = -I.. -I$(top_srcdir)/lib -DLOCATE_DB=\"$(LOCATE_DB)\"

LDADD = ../find/version.o ../lib/libfind.a

all:: ${ALL}

.c.o:
	$(CC) -c $(DEFS) $(INCLUDES) $(CPPFLAGS) $(CFLAGS) $<

$(locate_OBJECTS): ../config.h
$(frcode_OBJECTS): ../config.h
$(code_OBJECTS): ../config.h
$(bigram_OBJECTS): ../config.h
install:: install-programs

install-programs: $(PROGRAMS) $(SCRIPTS)
	$(top_srcdir)/mkinstalldirs $(bindir)
	for p in $(PROGRAMS) $(SCRIPTS); do \
	  $(INSTALL_PROGRAM) $$p $(bindir)/`echo $$p|sed '$(transform)'`; \
	done

uninstall:: uninstall-programs

uninstall-programs:
	for p in $(PROGRAMS) $(SCRIPTS); do \
	  rm -f $(bindir)/`echo $$p|sed '$(transform)'`; \
	done

install:: install-libprograms

install-libprograms: $(LIBPROGRAMS) $(LIBSCRIPTS)
	$(top_srcdir)/mkinstalldirs $(libexecdir)
	for p in $(LIBPROGRAMS) $(LIBSCRIPTS); do \
	  $(INSTALL_PROGRAM) $$p $(libexecdir)/`echo $$p|sed '$(transform)'`; \
	done

uninstall:: uninstall-libprograms

uninstall-libprograms:
	for p in $(LIBPROGRAMS) $(LIBSCRIPTS); do \
	  rm -f $(libexecdir)/`echo $$p|sed '$(transform)'`; \
	done

locate: $(locate_OBJECTS)
	$(CC) -o $@ $(locate_OBJECTS) $(LDADD) $(LDFLAGS) $(LIBS)

frcode: $(frcode_OBJECTS)
	$(CC) -o $@ $(frcode_OBJECTS) $(LDADD) $(LDFLAGS) $(LIBS)

code: $(code_OBJECTS)
	$(CC) -o $@ $(code_OBJECTS) $(LDADD) $(LDFLAGS) $(LIBS)

bigram: $(bigram_OBJECTS)
	$(CC) -o $@ $(bigram_OBJECTS) $(LDADD) $(LDFLAGS) $(LIBS)

install:: install-man

install-man:
	for man in $(MANS); do \
	  sect=`echo $$man|sed 's%.*\.\([0-9][a-z]*\)$$%\1%'`; \
	  inst=`basename $$man $$sect|sed '$(transform)'`$$sect; \
	  mdir=$(mandir)/man$$sect; \
	  $(top_srcdir)/mkinstalldirs $$mdir; \
	  echo installing $$man as $$mdir/$$inst; \
	  $(INSTALL_DATA) $(srcdir)/$$man $$mdir/$$inst; \
	  cdir=$(mandir)/cat$$sect; \
	  if test -d $$cdir; then \
	    echo formatting $$man as $$cdir/$$inst; \
	    $(NROFF) -man $(srcdir)/$$man > $$cdir/$$inst; \
	  fi; \
	done

uninstall:: uninstall-man

uninstall-man:
	for man in $(MANS); do \
	  sect=`echo $$man|sed 's%.*\(\.[0-9][a-z]*\)$$%\1%'; \
	  inst=`basename $$man $sect|sed '$(transform)'`.$$sect; \
	  mdir=$(mandir)/man$$sect; \
	  cdir=$(mandir)/cat$$sect; \
	  rm -f $$mdir/$$inst $$cdir/$$inst; \
	done

mostlyclean:
	rm -f *.o core

clean: mostlyclean
	rm -f $(PROGRAMS) $(LIBPROGRAMS) $(LIBFILES) $(TEXFILES) $(CLEANFILES)

distclean: clean
	rm -f Makefile *.tab.c $(DISTCLEANFILES)
	rm -f config.cache config.log config.status ${CONFIG_HEADER} stamp-h

realclean: distclean
	rm -f TAGS $(INFOS)

dist: $(DIST_FILES) $(DIST_DIRS)
	-mkdir ../`cat ../distname`/$(subdir)
	@for file in $(DIST_FILES); do \
	  echo linking $$file; \
	  ln $(srcdir)/$$file ../`cat ../distname`/$(subdir)/$$file || \
	    { echo copying $$file instead; cp -p $(srcdir)/$$file ../`cat ../distname`/$(subdir)/$$file;}; \
	done

check dvi info install uninstall::

tags:: TAGS

TAGS::
	cd $(srcdir); etags $(SOURCES)

# Tell versions [3.59,3.63) of GNU make to not export all variables.
# Otherwise a system limit (for SysV at least) may be exceeded.
.NOEXPORT:

$(PROGRAMS) $(LIBPROGRAMS): ../find/version.o ../lib/libfind.a

updatedb: updatedb.sh
	rm -f $@
	version=`sed -e '/version_string/!d' -e 's/[^0-9.]*\([0-9.]*\).*/\1/' -e q $(top_srcdir)/find/version.c`; \
	find=`echo find|sed '$(transform)'`; \
	frcode=`echo frcode|sed '$(transform)'`; \
	bigram=`echo bigram|sed '$(transform)'`; \
	code=`echo code|sed '$(transform)'`; \
	sed \
	-e "s,@bindir@,$(bindir)," \
	-e "s,@libexecdir@,$(libexecdir)," \
	-e "s,@LOCATE_DB@,$(LOCATE_DB)," \
	-e "s,@version@,$$version," \
	-e "s,@find@,$$find," \
	-e "s,@frcode@,$$frcode," \
	-e "s,@bigram@,$$bigram," \
	-e "s,@code@,$$code," \
	$(srcdir)/updatedb.sh > $@
	chmod +x $@

install::
	$(top_srcdir)/mkinstalldirs $(localstatedir)

frcode.o code.o locate.o: locatedb.h
locate.o: ../lib/fnmatch.h ../lib/getopt.h
