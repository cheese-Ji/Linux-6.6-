# Linux-6.6-
```
uname -r
```
查看当前内核版本

```
apt install git fakeroot build-essential ncurses-dev xz-utils libssl-dev bc flex libelf-dev bison dwarves
```
安装依赖

```
wget https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.6.6.tar.xz
```
下载Linux6.6内核版本

```
 tar -xvf linux-6.6.6.tar.xz
```
解压

```
make menuconfig 
```
启动配置界面，可以看出里面包含所有的内核组件，包括文件系统，网络，IO栈，虚拟化和设备驱动等等。由于我第一次接触，我选择直接保存，此配置就是内核驱动包含的配置文件
![image](https://github.com/cheese-Ji/Linux-6.6-/assets/155931600/f6752384-0168-4703-9060-7cef5be1c613)

```
 make -j 16
```
开始编译，等待编译完成（其中16为你自己虚拟机的cup线程，可以根据自己配置修改）

```
make modules_install
```

![image](https://github.com/cheese-Ji/Linux-6.6-/assets/155931600/0af6b92d-2735-41b5-99ca-87bbcd31eb45)

安装模块

```
make install
```
![image](https://github.com/cheese-Ji/Linux-6.6-/assets/155931600/b464ccac-550a-4386-82df-055607330850)

安装内核

```
update-grub
```


重启虚拟机


