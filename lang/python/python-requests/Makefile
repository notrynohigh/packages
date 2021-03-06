#
# Copyright (C) 2007-2019 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-requests
PKG_VERSION:=2.22.0
PKG_RELEASE:=1

PKG_MAINTAINER:=Josef Schlehofer <josef.schlehofer@nic.cz>, Alexandru Ardelean <ardeleanalex@gmail.com>
PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILES:=LICENSE
PKG_CPE_ID:=cpe:/a:python-requests:requests

PYPI_NAME:=requests
PKG_HASH:=11e007a8a2aa0323f5a921e9e6a2d7e4e67d9877e85773fba9ba6419025cbeb4

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

define Package/python-requests/Default
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=HTTP library for Python
  URL:=https://2.python-requests.org/
endef

define Package/python-requests
$(call Package/python-requests/Default)
  DEPENDS:= \
	  +PACKAGE_python-requests:python \
	  +PACKAGE_python-requests:python-chardet \
	  +PACKAGE_python-requests:python-idna \
	  +PACKAGE_python-requests:python-urllib3 \
	  +PACKAGE_python-requests:python-certifi
  VARIANT:=python
endef

define Package/python3-requests
$(call Package/python-requests/Default)
  DEPENDS:= \
	  +PACKAGE_python3-requests:python3-light  \
	  +PACKAGE_python3-requests:python3-chardet  \
	  +PACKAGE_python3-requests:python3-idna  \
	  +PACKAGE_python3-requests:python3-urllib3  \
	  +PACKAGE_python3-requests:python3-certifi
  VARIANT:=python3
endef

define Package/python-requests/description
  Requests is the only Non-GMO HTTP library for Python, safe for human consumption
endef

define Package/python3-requests/description
$(call Package/python-requests/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-requests))
$(eval $(call BuildPackage,python-requests))
$(eval $(call BuildPackage,python-requests-src))

$(eval $(call Py3Package,python3-requests))
$(eval $(call BuildPackage,python3-requests))
$(eval $(call BuildPackage,python3-requests-src))
