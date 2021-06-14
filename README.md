# 笔记信息
!> 这里记录了日常所用的一些笔记信息

# PC机安装linux CentOS6.10
## U盘启动盘制作
UltraISO制作U盘启动盘
1. 文件---打开 选择镜像文件
![alt](./images/centos_1.png)
2. 启动-写入硬盘映像-写入
![alt](./images/centos_2.png)
![alt](./images/centos_3.png)
1. 写入后就完成了，同理，不需要把镜像文件拷到U盘。  
   遇到问题：  
   在系统U盘启动后提示`Press the <ENTER> key to begin the installation process`的画面，不管是X86_64 ,还是i386版本，都是卡在这里。  
   用记事本打开这个文件`syslinux\syslinux.cfg`，把第一行`default vesamenu.c32`替换为`default linux timeout 600 label linux kernel vmlinuz append initrd=initrd.img`这样修改之后，系统启动的时候就会跳过安装菜单选项界面，直接进入到语言选择界面  

## 安装过程
1. 选择语言  
![alt](./images/centos_4.png)
![alt](./images/centos_5.png)
2. 选择语言键盘  
![alt](./images/centos_6.png)
![alt](./images/centos_7.png)
![alt](./images/centos_8.png)
3. 欢迎界面---下一步  
![alt](./images/centos_9.png)
4. 选择存储设备--下一步  
![alt](./images/centos_10.png)
5. 给计算机起名--下一步  
![alt](./images/centos_11.png)
6. 选择时区---下一步  
![alt](./images/centos_12.png)
7. 设置root密码---下一步  
![alt](./images/centos_13.png)
![alt](./images/centos_14.png)
8. 分区  
![alt](./images/centos_15.png)  
![alt](./images/centos_16.png)  
`/boot`分区`100mb`或者`200mb`  
![alt](./images/centos_17.png)  
`Swap（交换分区）`内存的1倍或者2倍 例如`2g内存`，swap分区设置为`2048`  
![alt](./images/centos_18.png)  
`/根分区`使用全部可用空间  
![alt](./images/centos_19.png)  
![alt](./images/centos_20.png)  
![alt](./images/centos_21.png)  
9. 点更改设备（千万注意引导程序安装的地方，引导写到电脑磁盘上的MBR，不是U盘的，千万注意）  
    `说明`:这一步至关重要,如果按照默认方式安装,会把系统启动引导安装到 U 盘里面,这也就是很多网友安装完系统之后,只要把 U 盘拔了,系统就启动不了,插上 U 盘系统又能正常启动的原因了!
    ![alt](./images/centos_22.png)  
    点`BIOS`驱动器顺序  
    ![alt](./images/centos_23.png)  
    第一`BIOS`驱动器:选择`本地磁盘驱动器`, 第二`BIOS`驱动器:选择`U盘驱动器`----点确定  
    ![alt](./images/centos_24.png)  
    ![alt](./images/centos_25.png)  
    定制系统软件`desktop`---现在自定义---下一步  
    ![alt](./images/centos_26.png)  
    Web环境  
    ![alt](./images/centos_27.png)  
    可扩展文件系统支持  
    ![alt](./images/centos_28.png)  
    基本系统  
    ![alt](./images/centos_29.png)  
    应用程序  
    ![alt](./images/centos_30.png)  
    开发、弹性存储、数据库、服务器可以都不勾，有需要，以后使用中有需要再手动安装  
    桌面  除了KDE，其他都选就可以  
    ![alt](./images/centos_31.png)  
    语言支持  
    ![alt](./images/centos_32.png)  
    系统管理、虚拟化、负载平衡器、高可用性可以都不选  
10. 完成配置，开始安装centos  
    ![alt](./images/centos_33.png)  
    ![alt](./images/centos_34.png)  
11. 安装完成，重新引导  
    ![alt](./images/centos_35.png)  
12. 欢迎引导页面  
    ![alt](./images/centos_36.png)  
13. 许可证  
    ![alt](./images/centos_37.png)  
14. 创建用户，可以先不创建，用root账户登录就行  
    ![alt](./images/centos_38.png)  
15. 时间和日期  
    ![alt](./images/centos_39.png)  
16. Kdump,去掉  
    ![alt](./images/centos_40.png)  
17. 重启后用root用户登录即可  
    ![alt](./images/centos_41.png)  