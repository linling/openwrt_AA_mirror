#
# Copyright (C) 2006-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=rpusbdisp

PKG_REV:=d79255bbf1a960330ac63298cd31820a2e00b001
PKG_VERSION:=20131119_$(PKG_REV)
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://github.com/robopeak/rpusbdisp/
PKG_SOURCE_PROTO:=git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_CAT:=zcat

PKG_BUILD_DIR:=$(KERNEL_BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

MAKE_PATH:=drivers/linux-driver

MAKE_VARS += KERNEL_SOURCE_DIR="$(LINUX_DIR)" \
		PWD="$(PKG_BUILD_DIR)/$(MAKE_PATH)"

RPUSBDISP_FILES:= $(PKG_BUILD_DIR)/$(MAKE_PATH)/rp_usbdisplay.ko

define KernelPackage/rpusbdisp
  SUBMENU:=Video Support
  TITLE:=Driver for RoboPeak Mini USB Display
  DEFAULT:=y
  DEPENDS:=@USB_SUPPORT +kmod-fb +kmod-fb-cfb-fillrect +kmod-fb-cfb-copyarea +kmod-fb-cfb-imgblt
  URL:=http://www.robopeak.com/
  FILES:=$(RPUSBDISP_FILES)
  AUTOLOAD:=$(call AutoLoad,08, \
  	fb \
  	syscopyarea \
  	sysfillrect \
  	fb_sys_fops \
  	sysimgblt \
        rp_usbdisplay \
  )
  MENU:=1
endef

define KernelPackage/rpusbdisp/description
 This package contains a driver for RoboPeak Mini USB Display
endef

$(eval $(call KernelPackage,rpusbdisp))
