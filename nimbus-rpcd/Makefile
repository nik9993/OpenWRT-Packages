include $(TOPDIR)/rules.mk

PKG_NAME:=nimbus-rpcd
PKG_VERSION:=0.1
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_URL:=
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE:=$(PKG_NAME).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=Nimbus-One
	CATEGORY:=Utilities
	TITLE:=RPCD tools for Nimbus One
	DEPENDS:=+rpcd
endef

define Package/$(PKG_NAME)/description
Nimbus One rpcd module:q

endef

define Package/$(PKG_NAME)/install
	#make libexec folder
	$(INSTALL_DIR) $(1)/usr/libexec/rpcd
	#add bash scripts
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/rpcd/* $(1)/usr/libexec/rpcd/.
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
