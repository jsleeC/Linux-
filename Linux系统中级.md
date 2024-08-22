**Linux 用户和权限**

1.Linux 的 root用户：

​	1.root用户（超级管理员）

​	![image-20240619113827720](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619113827720.png)

root用户拥有最大的系统操作权限，而普通用户在许多地方的权限是受限的。

普通用户的权限，一般在其HOME目录内是不受限的；一旦出了HOME目录，大多数地方，普通用户仅有**只读和执行权限**，**无修改权限**。

![image-20240619114421583](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619114421583.png)

**su - root （Switch User）** 切换root 用户，需要密码。su - 

![image-20240619123920874](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619123920874.png)

sudo 临时获得root权限，需要配置sudo认证。

![image-20240619124056905](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619124056905.png)

visudo jsong ALL=(ALL)	NOPASSWD:ALL

sudo mkdir jsong

2.用户和用户组：

​		1.理解用户、用户组概念

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619125120625.png" alt="image-20240619125120625" style="zoom:50%;" />

**用户组命令：groupadd : 添加用户组；groupdel : 删除用户组；**

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619125406050.png" alt="image-20240619125406050" style="zoom:50%;" />

**用户管理：useradd -g -d 用户组 ； userdel -r 用户名 ； id 用户名 ； usermod -aG 用户组  用户名**

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619125819720.png" alt="image-20240619125819720" style="zoom:80%;" />

**useradd test2 -g itcast -d /home/test222**

**su -  test2     pwd**

**userdel test2（不删除根目录）**

**userdel -r test（删除根目录）**

**id test3**

**usermod -aG TEST test1**（单个用户可以加入多个用户组）

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619130747924.png" alt="image-20240619130747924" style="zoom:50%;" />

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619130947362.png" alt="image-20240619130947362" style="zoom:50%;" />

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619131108822.png" alt="image-20240619131108822" style="zoom:50%;" />

3.查看权限控制信息：**查看Linux 文件权限管控信息，掌握读、写、执行三种权限含义**

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619132056987.png" alt="image-20240619132056987" style="zoom:50%;" />

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619132429649.png" alt="image-20240619132429649" style="zoom:50%;" />

**用户本身；用户组：用户组里面所有用户的操作权限；其他用户权限。**

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619132959811.png" alt="image-20240619132959811" style="zoom:50%;" />

**r:read ； w:修改；x：执行或cd 进入**

4.chmod 命令：**修改权限信息，使用数字序号标记权限。**

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619140730822.png" alt="image-20240619140730822" style="zoom:50%;" />

**chmod u=rwx,g=rx,o=x hello.txt**

**chmod -R u=rwx,g=rx,o=x test**

**权限：文件所属用户或root才可以修改权限。**

**可以用数字序号表示文件权限rwx**

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619142550656.png" alt="image-20240619142550656" style="zoom:50%;" />

**chmod 751 test.txt（user = 7（rwx） ； group = 5（r-x） ; other = 1（--x））**

chmod 515 hello.txt

chmod 326 hello.txt

123 ：--x -w- -wx

**权限序号谨记（r = 4 ; w = 2 ; x = 1）**数字序号相加即可。

**rwx = 7 ; rw- = 6；--x : 1** 

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619143720050.png" alt="image-20240619143720050" style="zoom:50%;" />

5.chown 命令：**修改权限控制，修改所属用户、用户组**， root执行

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240619144453778.png" alt="image-20240619144453778" style="zoom:50%;" />

**chown root hello.txt（用户）**

**chown :root hello.txt（用户组）**

**chown root:root hello.txt（用户和用户组）**

**chown -R root: root test（所有文件，用户和用户组）**

#### 				**<u>linux系统使用小技巧</u>**

**1.强制停止linux某些程序的运行：ctrl + c**

命令输入错误，也可以通过快捷键ctrl + c 退出当前输入，重新输入

**2.ctrl + d :退出或登录**

可以通过快捷键ctrl + d 退出账户的登录， exit也可以

或者退出某些特定程序的专属页面

ps:不能用于退出 vi/vim

**3.历史命令搜索 : history**

可以通过：！命令前缀，自动执行上一次匹配前缀的历史命令

可以通过快捷键：ctrl + r , 输入内容去匹配历史命令

如果搜索到的内容是你需要的，那么：1.回车键可以直接执行；2.键盘左右键，可以得到此命令（不执行）。

**4.光标移动快捷键：**

ctrl + a : 跳到命令开头；

ctrl + e : 跳到命令结尾；

ctrl + 键盘左键 : 向左跳一个单词；

ctrl + 键盘右键 : 向右跳一个单词；

**5.清屏**

通过快捷键ctrl + l ,可以清空终端内容；

或通过命令clear 得到同样效果。

![image-20240807210814997](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240807210814997.png)

 查看主机状态的命令：

**1.查看系统资源占用**

top命令查看CPU、内存使用情况，类似于Windows的任务管理器；

默认每5秒刷新一次，**语法：直接输入top即可，按q或ctrl+c退出**；

![image-20240811105215863](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811105215863.png)

![image-20240811105512891](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811105512891.png)

![image-20240811105651776](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811105651776.png)

![image-20240811110615750](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811110615750.png)

**2.磁盘信息监控：**

![image-20240811110744884](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811110744884.png)

![image-20240811110835927](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811110835927.png)

![image-20240811111019184](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811111019184.png)

**3.网络状态监控：**<u>rxkB/s 与 txkB/s  数据的接收与发送，网络速度</u>

![image-20240811111318568](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811111318568.png)

![image-20240811111717153](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811111717153.png)

**环境变量：**

命令就是一个个可执行程序；

![image-20240811112126060](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811112126060.png)

![image-20240811112417542](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811112417542.png)

![image-20240811112439321](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811112439321.png)

![image-20240811112831661](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811112831661.png)

永久有效：用户有效：

![image-20240811113245243](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811113245243.png)

全局有效：

![image-20240811113351094](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811113351094.png)

![image-20240811113519119](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811113519119.png)

$PATH：去原有的PATH的值；

![image-20240811114058125](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811114058125.png)

上传和下载：

![image-20240811115548210](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811115548210.png)

![image-20240811115849241](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811115849241.png)

**文件压缩和解压：**

![image-20240811120305653](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811120305653.png)

![image-20240811120510553](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811120510553.png)

![image-20240811120821487](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811120821487.png)

![image-20240811121458339](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811121458339.png)

![image-20240811122203752](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811122203752.png)

![image-20240811122450155](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811122450155.png)

![image-20240811122859242](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240811122859242.png)

