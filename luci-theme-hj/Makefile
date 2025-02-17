#
# Copyright (C) 2019-2024 The Sirpdboy Team <herboy2008@gmail.com>    
#
# This is free software, licensed under the Apache License, Version 2.0 .
#

include $(TOPDIR)/rules.mk

THEME_NAME:hj
THEME_TITLE:=hj Theme
PKG_NAME:=luci-theme-hj
LUCI_TITLE:=hj Theme by houjie
LUCI_DEPENDS:=+luci-base
PKG_VERSION:=2.2.6
PKG_RELEASE:=20250102

define Package/luci-theme-hj/postrm
#!/bin/sh
[ -n "$${IPKG_INSTROOT}" ] || {
	uci -q delete luci.themes.hj
	#uci -q delete luci.themes.Material3Red
	# uci -q delete luci.themes.Material3Dark
	# uci -q delete luci.themes.Material3Light
	uci commit luci
}
endef
define Package/luci-theme-hj/postrm-pkg
#!/bin/sh
[ -n "${IPKG_INSTROOT}" ] || { rm -f /tmp/luci-indexcache.*
	rm -rf /tmp/luci-modulecache/
	killall -HUP rpcd 2>/dev/null
        ln -s www/luci-static/hj /
	exit 0
}

}
endef

CONFIG_LUCI_CSSTIDY:=

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
