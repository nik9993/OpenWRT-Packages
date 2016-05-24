include $(TOPDIR)/rules.mk

PKG_NAME:=nimbus-utils
PKG_VERSION:=0.1
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_URL:= https://github.com/nik9993/nimbus-utils.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE:=$(PKG_NAME).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=Nimbus-One
	CATEGORY:=Utilities
	TITLE:=Nimbus-One Utilities
	DEPENDS:=+libubox +libubus
endef

define Package/$(PKG_NAME)/install
Nimbus One Utilities meant to be accessed by other packages
endef

define Package/$(PKG_NAME)/install
	#make nimbus folder
	$(INSTALL_DIR) $(1)/usr/lib/nimbus/
	#install binary
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/nimbus/* $(1)/usr/lib/nimbus/.
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
