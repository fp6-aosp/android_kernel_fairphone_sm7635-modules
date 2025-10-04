KERNEL_SRC ?= /lib/modules/$(shell uname -r)/build

M ?= $(shell pwd)

KBUILD_OPTIONS += HAPTIC_HV_ROOT=$(KERNEL_SRC)/$(M)
KBUILD_OPTIONS += CONFIG_AWINIC_HAPTIC_HV=m

all:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) modules $(KBUILD_OPTIONS)

modules_install:
	$(MAKE) INSTALL_MOD_STRIP=1 -C $(KERNEL_SRC) M=$(M) modules_install

clean:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) clean
