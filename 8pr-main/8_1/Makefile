# Top-level Makefile

SUBDIRS := libmysyslog myrpc-server myrpc-client

.PHONY: all clean deb

all:
	@for dir in $(SUBDIRS); do \
		$(MAKE) -C $$dir || exit 1; \
	done

clean:
	@for dir in $(SUBDIRS); do \
		$(MAKE) -C $$dir clean; \
	done

deb: all
	@mkdir -p deb
	$(MAKE) -C libmysyslog deb
	$(MAKE) -C myrpc-server deb
	$(MAKE) -C myrpc-client deb
