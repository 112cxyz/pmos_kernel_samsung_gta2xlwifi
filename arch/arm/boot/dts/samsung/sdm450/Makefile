# Samsung SDM450 Project

dtb-$(CONFIG_MACH_GTA2XLLTE_EUR_OPEN) += sdm450-sec-gta2xllte_eur_open-r00.dtb \
					sdm450-sec-gta2xllte_eur_open-r01.dtb \
					sdm450-sec-gta2xllte_eur_open-r02.dtb \
					sdm450-sec-gta2xllte_eur_open-r03.dtb \
					sdm450-sec-gta2xllte_eur_open-r04.dtb \
					sdm450-sec-gta2xllte_eur_open-r05.dtb

dtb-$(CONFIG_MACH_GTA2XLWIFI_EUR_OPEN) += sdm450-sec-gta2xlwifi_eur_open-r02.dtb \
					sda450-sec-gta2xlwifi_eur_open-r02.dtb \
					sda450-sec-gta2xlwifi_eur_open-r03.dtb \
					sda450-sec-gta2xlwifi_eur_open-r04.dtb \
					sda450-sec-gta2xlwifi_eur_open-r05.dtb

ifeq ($(CONFIG_ARM64),y)
always          := $(dtb-y)
subdir-y        := $(dts-dirs)
else
targets += dtbs
targets += $(addprefix ../, $(dtb-y))

$(obj)/../../%.dtb: $(src)/%.dts FORCE
        $(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../../,$(dtb-y))
endif
clean-files := *.dtb *.reserve.dts
