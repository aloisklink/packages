#
# Copyright (C) 2022 Alois Klink <alois@nquiringminds.com>
#

include $(TOPDIR)/rules.mk

PKG_NAME:=scipy
PKG_VERSION:=1.9.3
PKG_RELEASE:=1

PYPI_NAME:=$(PKG_NAME)
PKG_HASH:=fbc5c05c85c1a02be77b1ff591087c83bc44579c6d2bd9fb798bb64ea5e1a027

PKG_MAINTAINER:=Alois Klink <alois@nquiringminds.com>

PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE.txt
PKG_CPE_ID:=cpe:/a:scipy:scipy

# yes, zip... sigh
# PYPI_SOURCE_EXT:=zip
HOST_PYTHON3_PACKAGE_BUILD_DEPENDS:=Cython numpy

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-scipy
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Fundamental algorithms for scientific computing in Python
  URL:=https://www.numpy.org/
  DEPENDS:=@!SOFT_FLOAT +INSTALL_GFORTRAN:libgfortran +python3-numpy
endef

define Package/python3-scipy/description
SciPy (pronounced “Sigh Pie”) is an open-source software for mathematics,
science, and engineering. It includes modules for statistics, optimization,
integration, linear algebra, Fourier transforms, signal and image processing,
ODE solvers, and more.

By default, this package is built without some modules.
For some modules to be available, the INSTALL_GFORTRAN symbol needs
to be enabled in the OpenWrt core/toolchain.
endef

$(eval $(call Py3Package,python3-scipy))
$(eval $(call BuildPackage,python3-scipy))
$(eval $(call BuildPackage,python3-scipy-src))
