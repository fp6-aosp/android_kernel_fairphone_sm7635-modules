KERNEL_SRC ?= /lib/modules/$(shell uname -r)/build

M ?= $(shell pwd)

KBUILD_OPTIONS += HALL_KERNEL_ROOT=$(KERNEL_SRC)/$(M)
KBUILD_OPTIONS += CONFIG_HALL_DET=m

all:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) modules $(KBUILD_OPTIONS)

modules_install:
	$(MAKE) INSTALL_MOD_STRIP=1 -C $(KERNEL_SRC) M=$(M) modules_install

clean:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) clean
