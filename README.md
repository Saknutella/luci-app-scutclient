# luci-app-scutclient
* git clone到feeds/luci/applications
* 再执行./scripts/feeds install -a -p luci
* 然后make menuconfig
* 在feeds/luci/contrib/package中makefile加入
*   \$ (eval $(call application,luci-app-scutclient, 1.3,\
       +PACKAGE_luci-app-scutclient:libuci +libpthread +libubox +librt))
* 就可以在Luci的Applications看到编译选项
  需要luci-compat
* 有些会在编译的时候自己带一个luci-scutclient，那个会缺少nixio前缀导致报错，需要手动在applications/luci-app-scutclient/controller中的lua文件，11行fs前加入nixio.
* 重新编译
