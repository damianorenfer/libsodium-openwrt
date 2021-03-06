include $(TOPDIR)/rules.mk

PKG_NAME:=libsodium
PKG_VERSION:=0.4.5
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://download.libsodium.org/libsodium/releases
PKG_MD5SUM:=3a97d2c29ec0133e334036e3f19d0741
PKG_CAT:=zcat

PKG_FIXUP:=libtool autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libsodium
  SECTION:=libs
  CATEGORY:=Libraries
  DEFAULT:=y
  TITLE:=P(ortable|ackageable) NaCl-based crypto library
  URL:=https://github.com/jedisct1/libsodium
endef

define Package/libsodium/description
  NaCl (pronounced "salt") is a new easy-to-use high-speed software library for network communication, encryption, decryption, signatures, etc.
  NaCl's goal is to provide all of the core operations needed to build higher-level cryptographic tools.
  Sodium is a portable, cross-compilable, installable, packageable fork of NaCl (based on the latest released upstream version nacl-20110221), with a compatible API.
  The design choices, particularly in regard to the Curve25519 Diffie-Hellman function, emphasize security (whereas NIST curves emphasize "performance" at the cost of security), and "magic constants" in NaCl/Sodium have clear rationales.
  The same cannot be said of NIST curves, where the specific origins of certain constants are not described by the standards.
  And despite the emphasis on higher security, primitives are faster across-the-board than most implementations of the NIST standards.
endef

define Build/Configure
  $(call Build/Configure/Default, --disable-ssp)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/sodium
	$(CP) $(PKG_INSTALL_DIR)/usr/include/sodium.h $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/sodium/*.h $(1)/usr/include/sodium
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libsodium.{a,so*} $(1)/usr/lib
endef

define Package/libsodium/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libsodium.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libsodium))
