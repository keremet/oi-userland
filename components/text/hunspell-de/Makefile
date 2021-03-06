#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL)". You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright (c) 2016 Alexander Pyhalov
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		hunspell-de
COMPONENT_VERSION=	20151222
IPS_COMPONENT_VERSION=	2015.12.22
COMPONENT_PROJECT_URL=	https://www.j3e.de/ispell/igerman98/index_en.html
COMPONENT_SUMMARY=	Myspell and Hunspell spell dictionary files for German
COMPONENT_LICENSE=	GPLv2
COMPONENT_LICENSE_FILE=	hunspell/COPYING_GPLv2
COMPONENT_FMRI=	library/myspell/dictionary/de
COMPONENT_CLASSIFICATION	= System/Localizations

COMPONENT_SRC=            igerman98-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=        $(COMPONENT_SRC).tar.bz2
COMPONENT_ARCHIVE_HASH=        \
    sha256:5964178dc87b9be9dfe7cb256c2e35e139e86063225c19cb1fe2cc7cb11d7e4e
COMPONENT_ARCHIVE_URL=   https://www.j3e.de/ispell/igerman98/dict/$(COMPONENT_ARCHIVE)

include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/justmake.mk
include $(WS_TOP)/make-rules/ips.mk

COMPONENT_BUILD_TARGETS = hunspell-all

DESTDIR=/usr/share/spell/hunspell
LINKDIR=/usr/share/spell/myspell
FFDIR=/usr/lib/firefox/dictionaries
TBDIR=/usr/lib/thunderbird/dictionaries

CHALIASES=	de_LI
DEALIASES=	de_BE de_LU

$(SOURCE_DIR)/.installed:       $(BUILD_32)
	[ -d $(PROTO_DIR)$(DESTDIR) ] || mkdir -p $(PROTO_DIR)$(DESTDIR)
	[ -d $(PROTO_DIR)$(LINKDIR) ] || mkdir -p $(PROTO_DIR)$(LINKDIR)
	[ -d $(PROTO_DIR)$(FFDIR) ] || mkdir -p $(PROTO_DIR)$(FFDIR)
	[ -d $(PROTO_DIR)$(TBDIR) ] || mkdir -p $(PROTO_DIR)$(TBDIR)
	for file in $(BUILD_DIR_32)/hunspell/de_{AT,CH,DE}.{aff,dic}; do \
		cp $$file $(PROTO_DIR)$(DESTDIR)/; \
	done
	for alias in $(CHALIASES); do\
		ln -fs de_CH.aff $(PROTO_DIR)$(DESTDIR)/$$alias.aff; \
		ln -fs de_CH.dic $(PROTO_DIR)$(DESTDIR)/$$alias.dic; \
	done
	for alias in $(DEALIASES); do\
		ln -fs de_DE.aff $(PROTO_DIR)$(DESTDIR)/$$alias.aff; \
		ln -fs de_DE.dic $(PROTO_DIR)$(DESTDIR)/$$alias.dic;\
	done
	for file in `cd $(PROTO_DIR)/$(DESTDIR)/; ls`;  do\
		ln -fs ../../../..$(DESTDIR)/$$file $(PROTO_DIR)$(LINKDIR)/$$file; \
		ln -fs ../../../..$(DESTDIR)/$$file $(PROTO_DIR)$(FFDIR)/$$file; \
		ln -fs ../../../..$(DESTDIR)/$$file $(PROTO_DIR)$(TBDIR)/$$file; \
	done
	$(TOUCH) $@

build: $(BUILD_32)

install: $(SOURCE_DIR)/.installed
