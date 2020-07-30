# [virtualbox安装ubuntu16 LTS及其配置](https://www.cnblogs.com/luengmingbiao/p/10859905.html)



**目录**

- [一、下载安装VirtualBox](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_label0)
- 二、安装ubuntu 
  - [　  2.1 创建虚拟机](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_label1_0)
  - [　　2.2 配置root密码](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_label1_1)
  - [　　2.3 允许root用户远程登陆ssh](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_label1_2)
  - [　　2.4 安装VirtualBox虚拟机增强功能](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_label1_3)
  - [　　2.5 分配共享数据空间](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_label1_4)
- 三、通过xshell远程访问ubuntu
  - [　　3.1 官网下载xshell](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_label2_0)
  - [　　3.2 打开xshell，会出现一个界面框，这个界面框类似于DOS的界面，需要操控远程的主机，都是通过这个界面进行操作。](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_label2_1)
  - [　　3.3 新建连接](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_label2_2)
  - [　　3.4 点击连接](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_label2_3)

 

------

 

　　如果觉得文章有帮助，请给个赞~让更多有需要的人搜索到~ 

[回到顶部](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_labelTop)

## 一、下载安装VirtualBox

　　1. 从[官网下载VirtualBox](https://www.virtualbox.org/wiki/Downloads)，目前版本：VirtualBox 6.0.6 for Windows hosts x86/amd64

　　2. 下载好之后安装VirtualBox

　　3. 运行VirtualBox程序，如下图所示：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513171227981-794519219.png)

　　

　　4. 配置VirtualBox。按CTRL+G打开全局设定，然后根据需要可以设定虚拟电脑存储位置和界面语言：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513171855888-375139867.png)

 

[回到顶部](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_labelTop)

## 二、安装ubuntu 

　　在本次实验中，选用ubuntu-16.04.5 LTS版本进行安装。



### 　  2.1 创建虚拟机

　　运行VitualBox程序，点击“新建”按钮，新建一个虚拟机：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513173248390-1586941179.png)

 

　　虚拟机名称自定义，示例：hadoop-ubuntu，操作系统选择Linux，版本选择ubuntu（64-bit）,然后点击下一步：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513173828135-1142603484.png)

　　

 　设定虚拟机的内存，此内存既为虚拟机所占用的系统内存，可以随意修改，但不要超过系统内存的70%，不然会对自己的电脑负载很大。在这里，为了方便之后的大数据编程学习使用，将虚拟内存设为8G，然后点击下一步：

　　![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513174244776-686032078.png)

　　

　　为虚拟机创建一块虚拟硬盘。选择“现在创建虚拟硬盘”，并单击“创建”：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513174426540-1274907528.png)

 

　　选择虚拟硬盘文件类型，建议选择默认的VDI（VirtualBox磁盘映像），并点击”下一步“：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513174626605-651057510.png)

　　

　　选择“动态拓展”，并点击”下一步“，因为分配给虚拟机的内存空间较大，使用时逐渐占用磁盘空间，闲置时自动缩减比较合理，所以选择动态扩展类型。
![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513174650771-652621639.png)

 

　　选择虚拟硬盘大小时一定先确定保存所在位置磁盘的可用大小。可用空间为500G，虚拟硬盘大小设置为20G。单击“创建”。输入虚拟硬盘文件的名称，并选择保存位置：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513174815930-1545398178.png)

 

　　此时ubuntu虚拟机已经创建完成，也就是说ubuntu所需的硬件资源准备好了。

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513180448560-1741887746.png)

 

 

　　弹出下图对话框，选择启动盘。单击右侧文件夹小图标。

 　![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513181224615-273675440.png)

 　

　　选择虚拟光盘文件ubuntu-16.04.5-desktop-amd64.iso，单击“启动”：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513181251371-673880650.png)

 

　　进入安装界面，选择“中文简体”，选择“安装Ubuntu”：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513181506473-809558543.png)

 

　　选择“继续”。网络状况不好可以不选择“安装ubuntu时下载更新”：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513183221738-1460100533.png)

 

　　选择“清楚整个硬盘并安装ubuntu” 单击 “现在安装”：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513183354122-1296525432.png)

 

　　弹出警告框，选择”继续“：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513183418664-336314979.png)

 

 　安装过程中时区，用鼠标单击地图中的“中国”， 就会选择“上海”，单击“继续”：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513183701948-344656008.png)

 

 　语言选“汉语”：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513183727535-979247467.png)

 

　　输入个人信息：用户名、计算机名、密码等。然后点击继续，安装过程可能需要几十分钟，请耐心等待。

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513183825080-1995739496.png)

 

　　安装过程如下，等待安装完成：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513184024520-1374497862.png)

 

　　安装完毕，重启虚拟机：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513185301820-728419009.png)

 



### 　　2.2 配置root密码

　　重启进入系统后，ubuntu默认没有配置root权限密码的，此时需要通过终端命令配置root密码，命令如下：

```
# sudo passwd
```

　　首先先输入在上一步配置用户名的密码，然后输入新的unix密码，此密码是root管理员的密码，请妥善保存。

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513221656204-563281540.png)

 



### 　　2.3 允许root用户远程登陆ssh

　　新安装的Ubuntu 16.04系统中的openssh是不允许root用户登陆的，需要从配置文件允许root用户远程登陆ssh。

　　编辑ssh的配置文件，命令如下：

```
sudo vim /etc/ssh/sshd_config
```

　　![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190514145254463-1631120810.png)

 

　　将其换为PermitRootLogin yes，如下图所示：

　　![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190514145352518-1716034587.png)

 

　　保存退出，重启ssh

```
service sshd restart
```

 



### 　　2.4 安装VirtualBox虚拟机增强功能

　　进入ubuntu虚拟机系统，安装VirtualBox增强功能，这可以提高虚拟机的效率。首先点击VBox菜单栏的“设备”项，选择最下面的“安装增强功能”。

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513223916985-2085886808.png)

 

　　此时可以看到桌面多了一个光盘图标，如果没有，则重试这一步。然后打开终端，输入以下的命令：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513224139644-235747297.png)

 

 　等待几分钟后就安装成功。

 



### 　　2.5 分配共享数据空间

　　为了方便虚拟机和宿主机之间的数据传输，我们可以为虚拟机设置一个和主机共享的“数据空间”。VBox为我们提供这个功能。

　　在VBox主界面左侧选择刚刚创建好的虚拟机，点击上方的“设置”按钮，进入虚拟机配置界面。点击左侧“共享文件夹”按钮，在新窗口中任意选择一个本地文件夹作为共享文件夹。实例选择文件夹位置为D:\share，不要勾选“只读分配”，勾选自动挂载，然后固定挂载到ubuntu虚拟机的/mnt/share/目录下。单击“确定”，并关闭设置窗口。

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513220733209-1745453642.png)

　　

　　进入ubuntu虚拟机，通过终端命令在系统目录下创建/mnt/share目录，命令如下：

```
# sudo mkdir /mnt/share
# sudo mount -t vboxsf share /mnt/share
# sudo gedit /etc/fstab
```

 　然后在文本末尾添加一行下面的内容：

```
"share /mnt/share vboxsf rw,gid=100,uid=1000,auto 0 0"
```

　　现在打开/mnt/share文件夹和主机D:\share文件夹，可以看到与主机对应共享文件夹的内容了。

 ![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513235632951-1879260432.png)

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190513235707574-413600406.png)

 

　　到这，已经成功配置共享数据空间了。

 

[回到顶部](https://www.cnblogs.com/luengmingbiao/p/10859905.html#_labelTop)

## 三、通过xshell远程访问ubuntu

　  Xshell是一款强大的安全终端模拟软件，Xshell模拟了远程主机的操作，其实质就是通过访问和连接到远程主机，在本地实现对远程主机的操作。



### 　　3.1 [官网下载xshell](https://xshell.en.softonic.com/)



### 　　3.2 打开xshell，会出现一个界面框，这个界面框类似于DOS的界面，需要操控远程的主机，都是通过这个界面进行操作。

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190514144318502-659095592.png)

 



### 　　3.3 新建连接

　　![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190514144422820-833899978.png)

 

　　ssh端口默认是22，无须修改，名称随便起，主机号写ubuntu的ip：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190514154614977-1844836262.png)

 

　　

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

　　![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190514154916603-1483625334.png)

 



### 　　3.4 点击连接

　　输入用户名和密码（在这里我们用root用户登陆ubuntu），勾选记住用户名和密码方便下次连接。连接成功后界面如下：

![img](https://img2018.cnblogs.com/blog/1426803/201905/1426803-20190514155213539-1860197394.png)

 

　　到此已经成功安装好ubuntu虚拟机了，以及配置后续操作所需要的功能了。 

 

参考：

​    https://blog.csdn.net/u012732259/article/details/70172704/

​    https://jingyan.baidu.com/article/066074d615b8f4c3c31cb067.html

​    https://blog.csdn.net/sweet__dream/article/details/78234345