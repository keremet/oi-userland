#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#

#
# Copyright (c) 2013, Oracle and/or its affiliates. All rights reserved.
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		zope.interface
COMPONENT_VERSION=	3.3.0
COMPONENT_PROJECT_URL=	http://zope.org/Wikis/Interfaces/FrontPage
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
    sha256:c049ef6f0748a2db26c7d01de1566e52f048e5fa6fbbb8da90c43e55597a5075
COMPONENT_ARCHIVE_URL=	http://www.zope.org/Products/ZopeInterface/$(COMPONENT_VERSION)/$(COMPONENT_ARCHIVE)
COMPONENT_BUGDB=	python-mod/zope

include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/setup.py.mk
include $(WS_TOP)/make-rules/ips.mk

# common targets
build:          $(BUILD_32_and_64)

install:        $(INSTALL_32_and_64)

test:           $(NO_TESTS)

BUILD_PKG_DEPENDENCIES =        $(BUILD_TOOLS)

include $(WS_TOP)/make-rules/depend.mk
