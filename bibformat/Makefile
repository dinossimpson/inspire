# $Id$

include ../config.mk
-include ../config-local.mk

LIBFILES = *.py
PYDIR = $(LIBDIR)/python/invenio/

SUBDIRS = format_elements format_templates output_formats

all:
	$(foreach SUBDIR, $(SUBDIRS), cd $(SUBDIR) && make all && cd .. ;)
	@echo "Done.  Please run make test now."

test:
	$(foreach SUBDIR, $(SUBDIRS), cd $(SUBDIR) && make test && cd .. ;)
	@echo "Done.  Please run make install now."

install:
	$(foreach SUBDIR, $(SUBDIRS), cd $(SUBDIR) && make install && cd .. ;)

	$(INSTALL) -m 664 $(LIBFILES) $(PYDIR)
	@echo "Done.  You may want to restart Apache now."

clean:
	$(foreach SUBDIR, $(SUBDIRS), cd $(SUBDIR) && make clean && cd .. ;)
	@rm -f *.orig *~
	@echo "Done."