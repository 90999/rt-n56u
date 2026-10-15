#
# xfrpc Makefile for rt-n56u (Padavan)
#
include $(TOPDIR)/rules.mk

PKG_NAME:=xfrpc
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/liudf0716/xfrpc.git
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

CMAKE_OPTIONS += \
	-DCMAKE_SYSTEM_NAME=Linux \
	-DCMAKE_C_COMPILER=$(TARGET_CC) \
	-DCMAKE_CXX_COMPILER=$(TARGET_CXX) \
	-DCMAKE_INSTALL_PREFIX=/usr

include $(INCLUDE_DIR)/package.mk

define Package/xfrpc
  SECTION:=net
  CATEGORY:=Network
  TITLE:=xfrpc frp client
  DEPENDS:=+libjson-c +libevent2 +libopenssl
endef

define Package/xfrpc/description
  xfrpc, frp client for padavan
endef

define Build/Configure
	cd $(PKG_BUILD_DIR) && mkdir build && cd build && \
	cmake $(CMAKE_OPTIONS) ..
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)/build
endef

define Package/xfrpc/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/xfrpc $(1)/usr/bin/xfrpc
endef

$(eval $(call BuildPackage,xfrpc))
