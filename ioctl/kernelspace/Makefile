TARGET = ioctl_dev
obj-m += $(TARGET).o

KERNELDIR := /usr/src/linux-headers-$(shell uname -r)
PWD := $(shell pwd)

all:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules

check:
	/usr/src/linux-headers-4.4.0-34-generic/scripts/checkpatch.pl --no-tree -f $(TARGET).c include/$(TARGET).h

clean:
	rm -rf *.o *.ko *.order *.symvers *.mod.c .chdev.* .tmp_versions .*.cmd

