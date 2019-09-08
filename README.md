### 贝壳云 / 斐讯N1一键制作OpenWrt镜像脚本
#### Usage
1. 编译, 不会的可以去 [Lean's OpenWrt source](https://github.com/coolsnowwolf/lede "Lean's OpenWrt source")  
   target可以选"Raspberry Pi 3B/3B+" / "ARMv8 multiplatform"
2. 将编译好的固件放入到"openwrt"目录  
   注意: 固件格式只支持"rootfs.tar.gz"、"ext4-factory.img.gz"、"ext4-factory.img"、"root.ext4.gz"和"root.ext4"
3. 执行bash mk.sh, 默认输出路径"out/xxx.img"
4. 写入U盘启动OpenWrt

2019-09-05 更新：
【 添加贝壳云支持 】
--------------------------------------------------------------------------------
2019-08-10 更新：
【 1. 去除无用菜单项，操作更简洁 】
【 2. 调整BOOT分区为64M，删除无需文件，默认体积减小至320M 】
【 3. 添加一键安装至emmc脚本，运行 "sh install.sh"即可安装到emmc (不保证100%能用) 】
【 4. 新增"root.ext4.gz"和"root.ext4"格式支持 】
【 5. 优化脚本，速度更爆炸 】
ps：原仓库已删除，请重新git clone
--------------------------------------------------------------------------------
2019-07-10 更新：
【 1. 跟进XQ7大佬的armbian，支持FULLCONE NAT，具体参考 原帖 】
【 2. 修复bug，请 git pull 后使用 】
--------------------------------------------------------------------------------

经过大家的不屑努力，N1的OpenWrt系统日趋完美，感谢各路大神的默默付出！

大家应该对编译OpenWrt固件已经很熟悉了吧？

什么？你不会？
参考：
Lean的仓库
报名佐大的“跟着佐大学OpenWrt”

使用OpenWrt固件和Armbian镜像拼包制作可用于U盘启动的OpenWrt固件的教程论坛也有，那么为什么还要弄个一键制作脚本呢？

【 1. 简省操作、福利小白 】
【 2. 可以自定义镜像大小，使用修改Armbian镜像的方式固然可行，但是Armbian的镜像体积过于庞大 】
【 本脚本会根据用户输入来决定镜像大小 { boot分区 (128M)+ rootfs分区 (用户输入) } 】

使用方法：
1. 将脚本克隆到本地

git clone https://github.com/tuanqing/mknop


2. 将事先编译好的可用于N1的OpenWrt固件复制到openwrt目录
3. 执行脚本
bash mk.sh
