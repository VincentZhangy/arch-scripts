进入livecd, 先联网，要是无线网请执行 iwctl device list 可以查看出 网卡型号比如我的就是 wlan0, 然后 iwctl station wlan0 scan 扫描无wifi, 然后 iwctl station wlan0 get-networks获取wifi, 然后 iwctl station wlan0 connect xxx 链接wifi, 连上wifi后，配置国内源，vim /etc/pacman.d/mirrorlist 找到China 保留china的去掉其他的, 接下来 lsblk 一下，看看自己的磁盘，比如我的 磁盘
240414_10h03m26s_screenshot
240414_10h03m26s_screenshot
958×991 103 KB

。 然后进行分区，比如我的： cfdisk /dev/nvme0n1. 进入cfdisk 分两个磁盘。 1个100M 文件类型选 EFI， 剩下的全部为正常linux文件系统，接下来 clone 我的 脚本 GitHub - Liu-WeiHu/arch-scripts 23 ， 修改下 0 号脚本 适配自己，然后执行脚本， 执行结束 接着 arch-chroot /mnt 进入chroot. 修改 1号 脚本，执行1号 ，重启，接着 修改2号 ，执行2号, 重启 以用户 登陆。接下来就是装桌面，桌面可以用下面的 链接 GitHub - Liu-WeiHu/hyprdots at current 27 。clone 下来 进入 Script文件 执行 ./install.sh 就可以了。
