# 用一个gdb文件解决gdb打印STL问题

## [使用linux的GDB打印STL(vector,map,set..................)](https://www.cnblogs.com/silentNight/p/5466418.html)

在linux用gdb或者cgdb计较不爽的地方是无法打印STL的东西，所有啊去网上找了找解决方案https://www.douban.com/note/182826844/?qq-pf-to=pcqq.c2c

本帖把怎么配置这个东西写出了，万一以后忘了，可以回头找找。

首先是下载gdb文件 https://sourceware.org/gdb/wiki/STLSupport  ------》找到网页里面的

![img](https://images2015.cnblogs.com/blog/660635/201605/660635-20160506170246091-80172074.png) 然后点击进去下载stl_views_1.0.3.gdb![img](https://images2015.cnblogs.com/blog/660635/201605/660635-20160506170406466-1898205068.png)

接下来把这个东西当到linux下，位置随便放，我放到了我的用户目录下

![img](https://images2015.cnblogs.com/blog/660635/201605/660635-20160506170548138-7311774.png)

然后写一个小程序测试一下，

 

![img](https://images2015.cnblogs.com/blog/660635/201605/660635-20160506170823982-1145067926.png)

接着cgdb test 进入调试模式，然后加载刚才的stl_views_1.0.3.gdb

![img](https://images2015.cnblogs.com/blog/660635/201605/660635-20160506171037857-1649494198.png)

接着就可以看看pmap的命令了

![img](https://images2015.cnblogs.com/blog/660635/201605/660635-20160506171242669-1781564813.png)

pmap variable------------>打印variable这个map的定义和map里面的个数

pmap variable int  int(就是单纯的两个int) ------------>打印pmap的元素和map的个数

pmap variable int int 20------------>打印索引是20的map的值 和map的个数

pmap variable int int 20 200------->打印索引是20 值是200的map值和map的个数

![img](https://images2015.cnblogs.com/blog/660635/201605/660635-20160506172043279-1670911795.png)