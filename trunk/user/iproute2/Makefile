SRC_NAME=iproute2-5.12.0

THISDIR = $(shell pwd)

all:
	$(MAKE) -C $(SRC_NAME) V=1

clean:
	$(MAKE) -C $(SRC_NAME) clean

romfs:
	$(ROMFSINST) $(THISDIR)/$(SRC_NAME)/ip/ip /bin/ip
	$(ROMFSINST) -s /bin/ip /sbin/ip
	$(ROMFSINST) -s /tmp/musl/libc.so /lib/ld-musl-mipsel-sf.so.1
	$(ROMFSINST) -s /tmp/musl/libc.so /lib/ld.so.1
ifeq ($(CONFIG_FIRMWARE_INCLUDE_QOS),y)
	$(ROMFSINST) $(THISDIR)/$(SRC_NAME)/tc/tc /bin/tc
endif
