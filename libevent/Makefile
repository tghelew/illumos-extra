#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License, Version 1.0 only
# (the "License").  You may not use this file except in compliance
# with the License.
#
# You can obtain a copy of the license at COPYING
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at COPYING.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#
# Copyright 2018, Thierry Ghelew <tlux@ghelew.net>
#

VER =	libevent-2.1.8-stable

include ../Makefile.defs

BUILD64=	yes

PATCHES =	Patches/*

CPPFLAGS +=	-D__EXTENSIONS__

#
# We apply the same configuration as to pkgsrc 
#
AUTOCONF_ENV += \
	ac_cv_func_epoll_ctl=no


#
# It is important to make sure that screen has a prefix of /usr. When screen
# builds and prefix is not set, it runs which screen to determine the prefix. On
# the first build, this means that you will probably get /usr/bin/screen.
# However, on subsequent builds, you will get the one from the proto area. Even
# worse, if PATH were ever pathological, you could potentially get
# /opt/local/bin which would be terrible.
#
AUTOCONF_OPTS = \
	--prefix=$(AUTOCONF_PREFIX) \
	--disable-samples

AUTOCONF_OPTS.64 += \
	--libdir=$(AUTOCONF_PREFIX)/lib/64

include ../Makefile.targ

include ../Makefile.targ.autoconf

