
include $(TOPDIR)/rules.mk

PKG_NAME:=helloworld
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=Hello world -- print a snarky message
endef

define Package/$(PKG_NAME)/description
	If you can't figure out what this program does, you're probably brain-dead and need immediate medical attention.
endef

# ����Դ�뵽����Ŀ¼
define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)
endef

# ��װ
define Package/$(PKG_NAME)/install
	# ���·�����ϵ� /binĿ¼�����ڣ��򴴽�
	$(INSTALL_DIR) $(1)/bin
	# �ѱ����ĳ��򿽱���·������ /bin Ŀ¼
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/bin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))