
KBUILD_EXTRA_SYMBOLS := \
    $(OUT_DIR)/../sm7635-modules/fairphone/emkit/Module.symvers

KBUILD_OPTIONS+= TOUCH_ROOT=$(KERNEL_SRC)/$(M)
KBUILD_OPTIONS += MODNAME?=touch_dlkm

all:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) modules $(KBUILD_OPTIONS)

modules_install:
	$(MAKE) INSTALL_MOD_STRIP=1 -C $(KERNEL_SRC) M=$(M) modules_install

%:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) $@ $(KBUILD_OPTIONS) $(KBUILD_EXTRA_SYMBOLS)

clean:
	rm -f *.o *.ko *.mod.c *.mod.o *~ .*.cmd Module.symvers
	rm -rf .tmp_versions
