Linux系统入门

第一章：基础介绍

硬件与软件：软件：是用户和计算机硬件之间的接口和桥梁，用户通过软件与计算机进行交流。而操作系统，就是软件的一类。

操作系统：用户和计算机之间的桥梁，调度管理计算机硬件进行工作，相当于计算机的灵魂。

![image-20240610140444368](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240610140444368.png)

![image-20240610140725519](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240610140725519.png)

虚拟机：虚拟机获得Linux系统环境。 

借助虚拟化技术，我们可以在系统中，通过软件：模拟计算机硬件，并给虚拟硬件安装真实的操作系统。

![image-20240610152746361](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240610152746361.png)

WSL：计算机硬件直连，无需通过虚拟机虚拟硬件。

![image-20240610155031262](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240610155031262.png)

![image-20240610155253582](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240610155253582.png)

第二章：Linux 基础命令

1.目录结构：一个根目录 / ，树形结构

![image-20240613144026342](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240613144026342.png)

路径描述方式：/ 表示层次关系

![image-20240613144244014](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240613144244014.png)

linux 文件路径表示： /usr/local/hello.txt      注意：**开头 / 表示根目录**；后面 / 表示层级关系。

Windows文件路径表示：D:\data\work\hello.txt  注意：开头 D:  表示D盘；后面  \  表示层级关系。

![image-20240613145145993](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240613145145993.png)

2. linux 命令入门：

   1. linux 命令基础：

      命令行：即linux终端，是一种命令提示符页面。

      命令：linux程序。

       linux 命令基础格式：命令具有其通用的格式：

      **<u>command [-options] [parameter]</u>**

      command : 命令**<u>本身</u>**；

      -options : [可选，非必填] 命令的一些**<u>选项</u>**，可以通过选项控制命令的**行为细节**；

      parameter ： [可选，非必填] 命令的**<u>参数</u>**，多数用于命令的**指向目标等**。

      语法中 [ ] 表示可选的意思。

      示例：

      **ls  -l  /home/itheima** , ls是命令本身；-l是选项；/home/itheima是参数。

      以列表的形式，显示/home/itheima目录内的内容。

      **cp -r test1 test2** , cp是命令本身；-r是选项；test1和test2是参数。

      复制文件夹test1成为test2。

   2. ls命令入门：

      ![image-20240613151542618](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240613151542618.png)

      ![image-20240613152155790](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240613152155790.png)

      ![image-20240613152546798](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240613152546798.png)

   3. ls命令的参数和选项：

       参数 ：文件路径

       选项：-a : 表示all的意思，即列出全部文件（包含隐藏的文件/文件夹）；以 . 开头的文件，表示linux系统中隐藏文件/文件夹（只要以 . 开头，就能自动隐藏）。

      选项： -l: **以列表（竖向排列）的形式展示内容，并展示更多信息。**

      ![image-20240613154531742](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240613154531742.png)

      ![image-20240613154820109](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240613154820109.png)

      **<u>总结：-h ：显示文件大小，与-l合并使用，单独使用无效果。</u>**

      ![image-20240613155112269](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240613155112269.png)

3. 目录切换相关命令（cd/pwd）：

   **<u>1</u>**. cd命令切换工作目录：

   **<u>cd : change directory</u>**

   **<u>语法： cd [linux 路径]</u>** 

   cd 命令无需选项，只有参数，表示要切换到那个目录下；

   cd 命令直接执行，不写参数，表示回到用户的HOME目录。

   <u>**2**</u>. pwd命令展示当前工作目录：

   **<u>pwd : print work directory</u>** 输出当前所在的工作目录。

   pwd命令，无选项，无参数，直接输入pwd即可

4. 相对路径、绝对路径和特殊路径符：

   1.绝对路径写法：**以根目录为起点**，描述路径的一种写法，路径描述以 / 开头

   cd /home/itheima/desktop

   2.相对路径写法：**以当前路径为起点**，描述路径的一种写法，路径描述无需 / 开头

   cd desktop

​	   3.特殊路径符： .  :  当前目录；.. : 上一级目录；~ ：HOME目录。

![image-20240614140452223](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614140452223.png)

![image-20240614141409725](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614141409725.png)

 	cd ./test/hello.txt（cd test/hello.txt）cd ../test/hello.txt	cd ~/test/hello.txt

5. 创建目录命令（mkdir）:

   mkdir命令创建目录（文件夹）

   ![image-20240614142606587](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614142606587.png)

   mkdir itheima	mkdir /home/itheima/test	mkdir ./test2	mkdir ~/test3 

   **<u>-p : 创建文件夹的一整个链条文件夹</u>**

   **<u>mkdir -p itcast/good/666 自动创建itcast、good和666文件夹</u>**

   ![image-20240614144001675](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614144001675.png)

   mkdir -p ~/itcast/itheima/nice/666

6. 文件操作命令part1(touch、cat、more)

   **<u>touch命令：</u>**创建文件

   touch 创建文件： **touch Linux路径** ： 命令无选项，参数必选，表示要创建的文件路径，相对，绝对，特殊路径符均可以使用。

   touch test.txt

   文件夹为深色，文件为浅色；文件夹信息首字母为d，文件信息首字母为-；

   **<u>cat命令：</u>**查看文件内容

   **cat linux路径**  ： cat有必填参数，参数表示：被查看的文件路径，相对，绝对，特殊路径符都可以使用。

   cat test.txt

   **<u>more命令：</u>**

   ![image-20240614151444280](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614151444280.png)

   ![image-20240614151532482](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614151532482.png)

   **<u>文件操作命令行总结：</u>**

   ![image-20240614151923605](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614151923605.png)

7. 文件操作指令part2(cp、mv)

   <u>**cp : 文件复制**</u>

   ![image-20240614152341003](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614152341003.png)

   ​	cp test.txt test1.txt（文件复制）	cp -r itheima itheima1（文件夹复制，加-r）

   <u>**mv : 文件移动**</u>

   ![image-20240614153429555](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614153429555.png)

   **mv test.txt Desktop/**

   <u>**rm : 文件删除**</u>

   ![image-20240614153828765](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614153828765.png)

   一次性可以删除多个文件和文件夹

   rm test.txt（文件删除）

   rm -r test2（文件夹删除）

   **<u>通配符：*</u>**

   ![image-20240614155105866](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614155105866.png)

   -f : 强制删除

   ![image-20240614155203579](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614155203579.png)

   **<u>注意：</u>**

   ![image-20240614155621052](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614155621052.png)

8. 查找命令(which、find)

   命令其实是一个个二进制可执行程序：

   **which 要查找的命令**

   find命令:

   ![image-20240614160840808](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614160840808.png)

   **find  /  -name  "test"**

   通配符：

   ![image-20240614161308532](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614161308532.png)

   **find  /  -name  "*test"**

   find 命令 - 按文件大小查找文件

   ![image-20240614161805692](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240614161805692.png)

   **<u>注意：k / M / G</u>**

   find / -name "*CENTOS*"

   find /usr -size +100M

9. grep、wc和管道符

   **1.grep命令过滤文件内容：**

   ![image-20240617132750958](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617132750958.png)

   **grep -n "itheima" test.txt**

   **2.wc命令统计内容数量：**

   ![image-20240617133309813](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617133309813.png)

   **wc test.txt**

   2 11 59 test.txt

   文件行数、单词数、字节数、文件名

   wc -c test.txt

   wc -m test.txt

   wc -l test.txt

    

   **3.|管道符的概念和应用：**

   cat test.txt | grep itheima

   cat test.txt | wc -l

   ls /usr/bin | grep gt f

   ls -l /usr/bin | grep gt f

   ls -l /usr/bin | wc -l

   | ：**将左边的命令作为右边命令的输入**

   **嵌套使用，双重过滤：**

   **cat test.txt | grep itcast | grep itheima**

   **先查找itcast ,然后在查找到itcast 中的内容中再查找itheima**

   ![image-20240617135028026](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617135028026.png)

   cat test.txt | grep itcast | wc -l

   cat test.txt | grep itheima | wc -w

   ![image-20240617135559004](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617135559004.png)

10. echo和重定向符

    1.使用echo命令输出内容
    
    ![image-20240617140048045](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617140048045.png)
    
    2.反引号 ` 的使用
    
    ![image-20240617140342093](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617140342093.png)
    
    **反引号包围内容会被作为命令执行，而非普通字符。**
    
    
    
    3.tail命令跟踪文件更改
    
    ![image-20240617141112900](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617141112900.png)
    
    **tail -20 test.txt**
    
    **tail -f test.txt（实时追踪文件内容输入）按ctrl + c 结束命令**
    
    4.重定向符号的使用
    
    ![image-20240617140459883](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617140459883.png)
    
    ![image-20240617141019338](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617141019338.png)![image-20240617143856449](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617143856449.png)
    
    
    
    echo "我当前的工作目录是：`pwd`" > work.txt
    
    echo "hello linux" >> work.txt
    
    tail -f work.txt
    
    ![image-20240617145249468](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617145249468.png)

11.VI/VIM编辑器

![image-20240617145458612](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617145458612.png)

![image-20240617145603280](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617145603280.png)

![image-20240617145906655](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617145906655.png)

![image-20240617150025442](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617150025442.png)

**：w :保存；：q:退出；：wq:保存并退出。**

![image-20240617150850136](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617150850136.png)

**文字输入在光标的左侧**

![image-20240617151335003](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617151335003.png)

![image-20240617151825675](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617151825675.png)

![image-20240617152345272](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617152345272.png)

**<u>效率高/快速</u>**

![image-20240617152833837](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240617152833837.png)

