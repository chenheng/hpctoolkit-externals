#
#  SymtabAPI Makefile.
#
#  $Id$
#
include ../Makefile.conf

PKG_NAME = symtabAPI

PREREQS = binutils boost libelf libdwarf

PLATFORM := $(SYMTABAPI_PLATFORM)
export PLATFORM

SRC_DIR = dyninst
BUILD_SUBDIRS = common elf dwarf symtabAPI instructionAPI parseAPI

FETCH_COPY_FILES = cmake/optimization.cmake
POST_FETCH_CMD = ./post-fetch

ifneq ($(ALT_DYN_SRC_TREE),no)

# Alternate source tree from --with-dyninst-src=PATH
FETCH_CMD = ./fetch-copy $(ALT_DYN_SRC_TREE)

else

# 9.3.2 release tar file from distfiles plus a merge with the jump
# table multi slices branch.

FETCH_TARFILE = dyninst-lite-9.3.2.tar.bz2
EXTRA_PATCH_FILES = jump-table-slices jump-table-slices-2

endif

include ../build-utils/Makefile.inc
