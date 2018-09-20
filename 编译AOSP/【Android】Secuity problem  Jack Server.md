## Secuity problem  Jack Server


![](http://pbdkyxc0r.bkt.clouddn.com/a5a3317c-afe6-4c6c-8c1b-729279b7b3a8.png)
以上错误截图大家都不陌生了，下面是详细解决方案。    

大家请按如下要求配置自己的账户：
打开~/.jack文件可以看到如下内容：

![](http://pbdkyxc0r.bkt.clouddn.com/5935e095-c246-4bc4-99c8-ccebb6f362e6.png)

上图中有8072和8073两个端口，由于我们所有user都是配置成这个的，而服务器这个端口显然只能一个用户使
用，所以我们为不同用户配置不同的port应该就能解决问题，那么我们应用如何配置呢？
如 你是public1账号，那么就请配置成：
SERVER_PORT_SERVICE=8051
SERVER_PORT_ADMIN=9051
若是public2账号当然对应8052,9052一次类推，可参考如下表格：


|User ID |SERVER_PORT_SERVICE |SERVER_PORT_ADMIN|
|:--:|:--:|:--:|
|public1|8051|9051|
|public2|8052|9052|
|Public3|8053|9053|
|Public4|8054|9054|
|Public5|8055|9055|
|Public6|8056|9056|



请大家严格按照上面的对应关系修改，否则冲突还会编译报错的，请知悉。
 
当然具体怎么修改就简单了，如下命令：vi ~/.jack 或vnc 下gedit ~/.jack