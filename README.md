luci-app-frpc
===

frpc的管理界面
代码参考 http://www.right.com.cn/forum/thread-306836-1-1.html 以及明月永在的界面


编译
---

直接从 OpenWrt/LEDE 的源码编译  
```bash
cd OpenWrt-SDK
# Clone 项目
git clone https://github.com/LinEvil/luci-app-frpc.git feeds/luci/applications/luci-app-frpc
# 下载安装feeds更新
./scripts/feeds update -a
./scripts/feeds install -a
# 编译 po2lmo 并复制到主目录 (如果有po2lmo可跳过)
pushd package/feeds/luci/luci-app-frpc/tools/po2lmo
make && sudo make install 
popd
cp /usr/bin/po2lmo ./
# 开始编译
make package/feeds/luci/luci-app-frpc/compile V=s
```
生成的文件在 bin/packages/系列名/luci/ 下面
