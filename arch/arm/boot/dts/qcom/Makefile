
dtb-$(CONFIG_ARCH_SDXPOORWILLS) += sdxpoorwills-rumi.dtb \
	sdxpoorwills-cdp.dtb \
	sdxpoorwills-mtp.dtb \
	sdxpoorwills-atp.dtb \
	sdxpoorwills-ttp.dtb \
	sdxpoorwills-cdp-256.dtb \
	sdxpoorwills-mtp-256.dtb \
	sdxpoorwills-dualwifi-cdp.dtb \
	sdxpoorwills-dualwifi-mtp.dtb \
	sdxpoorwills-pcie-ep-cdp-256.dtb \
	sdxpoorwills-pcie-ep-mtp-256.dtb \
	sdxpoorwills-pcie-ep-cdp.dtb \
	sdxpoorwills-pcie-ep-mtp.dtb \
	sdxpoorwills-v2-mtp.dtb \
	sdxpoorwills-v2-cdp.dtb

dtb-$(CONFIG_ARCH_MDM9650) += mdm9650-nand-mtp.dtb \
	mdm9650-ttp.dtb \
	mdm9650-v1.1-nand-mtp.dtb \
	mdm9650-v1.1-nand-dualwifi-mtp.dtb \
	mdm9650-v1.1-nand-ccard-v2.dtb \
	mdm9650-v1.1-emmc-pcie-ep-mtp.dtb \
	mdm9650-v1.1-nand-pcie-ep-mtp.dtb \
	mdm9650-v1.1-nand-cv2x.dtb \
	mdm9650-v1.1-nand-rome-sdio-mtp.dtb

dtb-$(CONFIG_ARCH_SDX20) += sdx20-emmc-cdp.dtb \
	sdx20-emmc-mtp.dtb \
	sdx20-nand-cdp.dtb \
	sdx20-nand-mtp.dtb \
	sdx20-nand-dualwifi-mtp.dtb \
	sdx20-nand-dualwifi-cdp.dtb \
	sdx20-v2-emmc-cdp.dtb \
	sdx20-v2-emmc-mtp.dtb \
	sdx20-v2-nand-cdp.dtb \
	sdx20-v2-nand-mtp.dtb \
	sdx20-v2-nand-dualwifi-mtp.dtb \
	sdx20-v2-nand-dualwifi-cdp.dtb \
	sdx20-v2-nand-singlewifi-dualwificonf-mtp.dtb \
	sdx20-emmc-pcie-ep-mtp.dtb \
	sdx20-nand-pcie-ep-mtp.dtb \
	sdx20-v2-emmc-pcie-ep-mtp.dtb \
	sdx20-v2-nand-pcie-ep-mtp.dtb

dtb-$(CONFIG_ARCH_MSM8937) += msm8937-rumi.dtb \
	msm8937-pmi8950-cdp.dtb \
	msm8937-pmi8937-cdp.dtb \
	msm8937-pmi8940-cdp.dtb \
	msm8937-pmi8950-ext-codec-cdp.dtb \
	msm8937-pmi8950-mtp.dtb \
	msm8937-pmi8937-mtp.dtb \
	msm8937-pmi8940-mtp.dtb \
	msm8937-pmi8950-rcm.dtb \
	msm8937-pmi8937-rcm.dtb \
	msm8937-pmi8940-rcm.dtb \
	msm8937-pmi8950-qrd-sku1.dtb \
	msm8937-pmi8937-qrd-sku2.dtb \
	msm8937-pmi8950-qrd-sku1-dvt1.dtb \
	msm8937-pmi8937-qrd-sku2-dvt1.dtb \
	apq8037-pmi8950-cdp.dtb \
	apq8037-pmi8937-cdp.dtb \
	apq8037-pmi8950-mtp.dtb \
	apq8037-pmi8937-mtp.dtb

dtb-$(CONFIG_ARCH_MSM8917) += msm8917-rumi.dtb \
	apq8017-pmi8937-cdp.dtb \
	apq8017-pmi8937-mtp.dtb \
	apq8017-pmi8950-cdp.dtb \
	apq8017-pmi8950-mtp.dtb \
	msm8917-pmi8937-cdp.dtb \
	msm8917-pmi8937-mtp.dtb \
	msm8917-pmi8940-cdp.dtb \
	msm8917-pmi8940-mtp.dtb \
	msm8917-pmi8950-cdp.dtb \
	msm8917-pmi8950-cdp-mirror-lake-touch.dtb \
	msm8917-pmi8950-ext-codec-cdp.dtb \
	msm8917-pmi8950-mtp.dtb \
	msm8917-pmi8937-rcm.dtb \
	msm8917-pmi8940-rcm.dtb \
	msm8917-pmi8950-rcm.dtb \
	msm8917-qgp-tmo.dtb \
	msm8917-pmi8937-qrd-sku5.dtb \
        msm8917-pmi8937-qrd-sku5_S88503.dtb \
	apq8017-pmi8937-cdp-wcd-rome.dtb \
	apq8017-pmi8950-cdp-wcd-rome.dtb \
	apq8017-no-pmi-wcd-rome-cdp.dtb 

dtb-$(CONFIG_ARCH_MDM9607) += mdm9607-mtp.dtb \
	mdm9607-ttp.dtb

targets += dtbs

include $(srctree)/arch/arm64/boot/dts/qcom/Makefile
$(obj)/%.dtb: $(src)/../../../../arm64/boot/dts/qcom/%.dts FORCE
	$(call if_changed_dep,dtc)

ifeq ($(CONFIG_BUILD_ARM64_DT_OVERLAY),y)
$(obj)/%.dtbo:$(src)/../../../../arm64/boot/dts/qcom/%.dts FORCE
	$(call if_changed_dep,dtc)
	$(call if_changed,dtbo_verify)

dtbs: $(addprefix $(obj)/,$(dtb-y)) $(addprefix $(obj)/,$(dtbo-y))
else
dtbs: $(addprefix $(obj)/,$(dtb-y))
endif
clean-files := *.dtb
