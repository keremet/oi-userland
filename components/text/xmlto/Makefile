#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2016 Alexander Pyhalov
# 

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME= 	xmlto
COMPONENT_VERSION= 	0.0.28
COMPONENT_SUMMARY= 	xmlto is a shell-script tool for converting XML files to various formats
COMPONENT_SRC= 		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE= 	$(COMPONENT_SRC).tar.bz2
COMPONENT_ARCHIVE_HASH= \
  sha256:1130df3a7957eb9f6f0d29e4aa1c75732a7dfb6d639be013859b5c7ec5421276
COMPONENT_ARCHIVE_URL= \
  https://fedorahosted.org/releases/x/m/xmlto/$(COMPONENT_ARCHIVE)
COMPONENT_PROJECT_URL = https://fedorahosted.org/xmlto/

include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

CONFIGURE_ENV += GETOPT=/usr/gnu/bin/getopt

# Strip compilation lines from test output
COMPONENT_TEST_TRANSFORMS += \
	'-e "s|^.*$(CC).*$$|XXX_CC_XXX|g" ' \
	'-e "s|^.*source=.*libtool=no.*$$|XXX_CC_XXX|g" ' \
	'-e "s|^.*DEPDIR=.deps.*$$|XXX_CC_XXX|g" ' \
	'-e "s|^.*xmlif.l.*$$|XXX_CC_XXX|g" ' \
	'-e "s|^make.*: Leaving directory.*$$|XXX_CC_XXX|g" ' \
	'-e "s|^make.*: Entering directory.*$$|XXX_CC_XXX|g" ' \
	'-e "/^XXX_CC_XXX$$/d" '

build: $(BUILD_32)

install: $(INSTALL_32)

test: $(TEST_32)
