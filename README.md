# luci-app-scutclient
* git clone到feeds/luci/applications
* 再执行./scripts/feeds install -a -p luci
* 然后make menuconfig
* 在feeds/luci/contrib/package中makefile加入
*   \$ (eval $(call application,luci-app-scutclient, 1.3,\
       +PACKAGE_luci-app-scutclient:libuci +libpthread +libubox +librt))
* 就可以在Luci的Applications看到编译选项
  需要luci-compat
