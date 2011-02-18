
ifeq ($(KVER),)
KVER := $(shell uname -r)
endif
KDIR := /lib/modules/$(KVER)/build
KDST := $(DESTDIR)/lib/modules/$(KVER)/kernel/drivers/input/keyboard

obj-m += atkbd-front.o

all:
	make -C $(KDIR) M=$(PWD) modules

clean:
	make -C $(KDIR) M=$(PWD) clean

install:
	install -c -D -m 744 atkbd-front.ko $(KDST)

