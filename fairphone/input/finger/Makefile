KERNEL_SRC ?= /lib/modules/$(shell uname -r)/build

M ?= $(shell pwd)

KBUILD_OPTIONS += FINGER_ROOT=$(KERNEL_SRC)/$(M)
KBUILD_OPTIONS += CONFIG_INPUT_FINGERPRINT=y
KBUILD_OPTIONS += CONFIG_FINGER_FOCAL=m

all:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) modules $(KBUILD_OPTIONS)

modules_install:
	$(MAKE) INSTALL_MOD_STRIP=1 -C $(KERNEL_SRC) M=$(M) modules_install

clean:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) clean
