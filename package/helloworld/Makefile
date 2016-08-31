# 根目录/rules.mk
include $(TOPDIR)/rules.mk

PKG_NAME:=helloworld
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=utils
	# 主菜单
	CATEGORY:=Utilities
	# 子菜单
	SUBMENU:=d7kj packages
	TITLE:=Hello world -- print a snarky message
endef

define Package/$(PKG_NAME)/description
	If you can't figure out what this program does, you're probably brain-dead and need immediate medical attention.
endef

# 拷贝源码到编译目录
define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)
endef

# 安装
define Package/$(PKG_NAME)/install
	# 如果路由器上的 /bin目录不存在，则创建
	$(INSTALL_DIR) $(1)/bin
	# 把编译后的程序拷贝到路由器的 /bin 目录
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/bin
endef

# 下面逗号不能有空格
$(eval $(call BuildPackage,$(PKG_NAME)))
