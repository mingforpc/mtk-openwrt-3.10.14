
include $(TOPDIR)/rules.mk

PKG_NAME:=libexif
PKG_VERSION:=0.6
PKG_RELEASE:=21

include $(INCLUDE_DIR)/package.mk

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

define Package/libexif
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=libexif
  URL:=https://github.com/libexif/libexif
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)/lib
	mkdir -p $(PKG_BUILD_DIR)/include
	$(CP) -R ./lib/* $(PKG_BUILD_DIR)/lib
	$(CP) -R ./include/* $(PKG_BUILD_DIR)/include
endef

define Build/Compile
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/include/
	mv lib/* $(1)/usr/lib/
	mv include/* $(1)/usr/include/
endef

define Package/libexif/install
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) -R $(PKG_BUILD_DIR)/lib/libexif.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libexif))
