#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-urllib3
PKG_VERSION:=1.24.1
PKG_RELEASE:=2
PKG_LICENSE:=MIT

PKG_SOURCE:=urllib3-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/u/urllib3
PKG_HASH:=de9529817c93f27c8ccbfead6985011db27bd0ddfcdb2d86f3f663385c6a9c22
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-urllib3-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-urllib3/Default
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=HTTP library with thread-safe connection pooling, file post, and more.
  URL:=https://urllib3.readthedocs.io/
endef

define Package/python-urllib3
$(call Package/python-urllib3/Default)
  DEPENDS:=+PACKAGE_python-urllib3:python
  VARIANT:=python
endef

define Package/python-urllib3/description
  HTTP library with thread-safe connection pooling, file post, and more.
endef

define Package/python3-urllib3
$(call Package/python-urllib3/Default)
  DEPENDS:=+PACKAGE_python3-urllib3:python3
  VARIANT:=python3
endef

define Package/python3-urllib3/description
$(call Package/python-urllib3/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-urllib3))
$(eval $(call BuildPackage,python-urllib3))
$(eval $(call BuildPackage,python-urllib3-src))
$(eval $(call Py3Package,python3-urllib3))
$(eval $(call BuildPackage,python3-urllib3))
$(eval $(call BuildPackage,python3-urllib3-src))