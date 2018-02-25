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

VER =	tmux-2.6

AUTOCONF_DIR = $(DESTDIR)$(AUTOCONF_PREFIX)

include ../Makefile.defs

# Autoconf uses pkg-config to detect libs and cflags since we are
# using $(AUTOCONF_DIR) during our build the value in pkg-config is
# inadequate.
AUTOCONF_ENV += \
	LIBEVENT_CFLAGS="-I$(AUTOCONF_DIR)/include" \
	LIBEVENT_LIBS="-L$(AUTOCONF_DIR)/lib -levent" \
	LIBNCURSES_CFLAGS="-I$(AUTOCONF_DIR)/gnu/include -I$(AUTOCONF_DIR)/include/ncurses" \
	LIBNCURSES_LIBS="-L$(AUTOCONF_DIR)/gnu/lib" \
	LIBTINFO_CFLAGS="-I$(AUTOCONF_DIR)/gnu/include" \
	LIBTINFO_LIBS="-L$(AUTOCONF_DIR)/gnu/lib -ltinfo"

include ../Makefile.targ

include ../Makefile.targ.autoconf

# usefull debug directive courtesy of:
# https://blog.melski.net/2010/11/30/makefile-hacks-print-the-value-of-any-variable/ 

print-%:
	@echo '$*=$($*)'

