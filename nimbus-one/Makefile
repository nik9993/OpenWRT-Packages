include $(TOPDIR)/rules.mk

PKG_NAME:=nimbus-one
PKG_VERSION:=0.1
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_URL:= https://github.com/nik9993/nimbus-one.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE:=$(PKG_NAME).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=Nimbus-One Service
	DEPENDS:=+nimbus-utils +nimbus-rpcd
endef

define Package/$(PKG_NAME)/description
Nimbus One Service that manages execution flow
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)
endef

define Build/Configure
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) $(TARGET_CONFIGURE_OPTS)
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/nimbus-one $(1)/bin/
    $(INSTALL_DIR) $(1)/etc/init.d
    $(INSTALL_BIN) $(PKG_BUILD_DIR)/nimbus $(1)/etc/init.d/nimbus
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
