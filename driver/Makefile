#  Copyright (C) 2011  caoweigang <caoweigang@longcheer.net> <caowai@gmail.com>
#
#  This is free software; you can redistribute it and/or modify
#  it under the terms of Version 2 of the GNU General Public License as
#  published by the Free Software Foundation.

obj-m := lctserial.o
KDIR := /lib/modules/$(shell uname -r)/build
MODULE_DIR := /lib/modules/$(shell uname -r)/kernel/drivers/usb/serial/
PWD := $(shell pwd)

default:
	$(MAKE) -C $(KDIR) SUBDIRS=$(PWD) modules

clean:
	rm -rf *.mod.c *.o *.markers *.symvers *.order  *.ko .tmp_versions .*.cmd

install:
	cp -f *.ko $(MODULE_DIR)
	depmod
uninstall:
	rm /lib/modules/$(shell uname -r)/kernel/drivers/usb/serial/lctserial.ko
	depmod
	rmmod lctserial 
	
	




