#
# Copyright (C) 2010-2012 Ling <ling.lin@robopeak.org>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=rp-serial-tcp-bridge
PKG_VERSION:=2013-11-11
PKG_RELEASE=1


include $(INCLUDE_DIR)/package.mk

define Package/rp-serial-tcp-bridge
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=RP Serial TCP bridge
  DEPENDS:=+libstdcpp +libpthread +librt
  URL:=http://www.robopeak.org
endef

define Package/rp-serial-tcp-bridge/description
 RP serial tcp bridge is a tiny TCP server for accessing Seiral PORT
endef

define Build/Compile
endef

define Build/Configure
endef

define Package/rp-serial-tcp-bridge/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) ./files/serial2tcp_bridge $(1)/usr/bin/serial2tcp_bridge
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) ./files/libinfra_core.so $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) ./files/ref/libconfig++.so.9 $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) ./files/ref/libusb-1.0.so.0 $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_CONF) ./files/etc/rp.conf $(1)/etc/
endef

$(eval $(call BuildPackage,rp-serial-tcp-bridge))
