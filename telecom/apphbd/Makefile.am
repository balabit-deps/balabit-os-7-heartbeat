#
# heartbeat: Linux-HA telecom code: application heartbeat daemon
#
# Copyright (C) 2002 Alan Robertson
#
# This program is free software; you can redistribute it and/or
# modify it under the terms of the GNU General Public License
# as published by the Free Software Foundation; either version 2
# of the License, or (at your option) any later version.
# 
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA  02111-1307, USA.
#
MAINTAINERCLEANFILES    = Makefile.in

AM_CPPFLAGS		= -I$(top_builddir)/include -I$(top_srcdir)/include \
			-I$(top_builddir)/libltdl -I$(top_srcdir)/libltdl \
			-I$(top_builddir)/linux-ha -I$(top_srcdir)/linux-ha

hadir			= $(sysconfdir)/ha.d
halibdir		= $(libdir)/@HB_PKG@
commmoddir		= $(halibdir)/modules/comm
halibexecdir		= $(libexecdir)/@HB_PKG@
havarlibdir		= $(localstatedir)/lib/@HB_PKG@
PIDFILE			= $(localstatedir)/run/apphbd.pid

COMMONLIBS		= -lplumb	\
			$(GLIBLIB)					\
			-lpils


LIBRT 			= @LIBRT@
AM_CFLAGS			= @CFLAGS@	\
			-DPIDFILE='"$(PIDFILE)"'


## binary progs
halibexec_PROGRAMS	= apphbd apphbtest

## SOURCES

apphbd_SOURCES	= apphbd.c
#
#	We don't really need libpils/libltdl (yet...)
#
apphbd_LDADD		= $(COMMONLIBS) 				\
			-lpils		\
			@LIBLTDL@ $(LIBRT)				


apphbd_LDFLAGS	= @LIBADD_DL@ @LIBLTDL@ -export-dynamic	@DLOPEN_FORCE_FLAGS@

## SOURCES
apphbtest_SOURCES	= apphbtest.c
apphbtest_LDADD		= $(COMMONLIBS) 				\
			$(top_builddir)/lib/apphb/libapphb.la		


apphbtest_LDFLAGS	=
