THISDIR = $(shell pwd)

all:
	echo xxm
	pwd
romfs:
	find / -name f0
	$(ROMFSINST) -p +x $(THISDIR)/f0 /usr/bin/f0
	$(ROMFSINST) -p +x $(THISDIR)/s0 /usr/bin/s0
