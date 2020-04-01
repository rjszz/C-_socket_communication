# C++ 简单的socket通信 面向对象

## 环境

编译：需要有 C++11 的编译环境

运行：最高需要 `GLIBCXX_3.4.22` 的动态运行库(已存放在`libstdc++`,具体用法请看目录下的`README.md`)

## Server 类(Server文件夹中)

   服务器端

   定义了Socket(),Bind(),Listen(),Handle(),start(),stop()6个类方法，分别用来进行Socket初始化，绑定，监听，启动和停止。

   其中`Handel`是Server进行的动作，我这里设计的是显示客户端发来的数据，需要更改的可以在此方法中进行更改可以扩充

## Client 类(Client文件夹中)

   客户端

   定义了Socket(),Connet(),handle(),start(),stop()5个类方法，分别用来进行Socket初始化以及连接，启动和停止

   同样的`handel`是Clien的动作，这里是向服务器发送一段话，需要更改的可以在此方法中进行更改可以扩充

## 使用

   - 1、分别在`Server`与`Client`目录下 下使用 `make`,来进行编译
   - 2、先使用`./server` 来开始服务器程序，可以将此文件夹部署在服务器
   - 3、再使用 `./client <ip address> <port>`来启动客户端程序，其中`<ip address>`是ip地址，如果是本地，请填写`127.0.0.1`,`<port>`是服务器的端口



————————————————————————————————————————————————

## 2020-3-26 更新

1、更改了`server`与`client`的handle方法

现在的功能是，客户端发送一句话，用户端可以回复相同的话



2、增加了退出指令

在客户端输入`exit`即可退出程序



3、服务器添加了`用户连接`与`用户断开`的提示



4、修复了客户端断开，服务端不断循环的bug



5、客户端新增了支持`空串输入`输入之后不会有任何影响



————————————————————————————————————————————————

## 2020-3-30 更新

增加了多线程的支持，可以多个客户端同时进行连接



客户端的使用方法一样



————————————————————————————————————————————————

实现了`聊天室`的功能，可以允许多个客户端在同一聊天室下进行聊天



**BUG Warning**:

1、如果输入的是英文字符，那么前三个字符不能进行删除，否则会有乱码

2、如果输入的是中文，由于终端输入的原因，进行删除很容易出现编码错误

<u>因此在非必要情况下请不要进行`删除(Backspace)`操作</u>		





​	