
安装maven

Maven的下载地址：http://maven.apache.org/download.cgi
这里以最新的3.2.3版本为例进行安装，在这之前需要确保机器上已经安装了JDK。

首先下载Maven并解压，并移动到usr/local目录下

$ wget http://mirror.bit.edu.cn/apache/maven/maven-3/3.2.3/binaries/apache-maven-3.2.3-bin.tar.gz
$ tar vxf apache-maven-3.2.3-bin.tar.gz
$ mv apache-maven-3.2.3 /usr/local/maven
修改环境变量，在/etc/profile中添加以下几行

MAVEN_HOME=/usr/local/maven
export MAVEN_HOME
export PATH=${PATH}:${MAVEN_HOME}/bin
记得执行source /etc/profile使环境变量生效。

最后运行mvn -v验证maven是否安装成功


ubuntu 安装chrome
64位
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb

sudo dpkg -i google-chrome*; sudo apt-get -f install

然后就可以使用了
/usr/bin/google-chrome-stable 

ubuntu teamViewer安装

进入官网，找到下载地址https://www.teamviewer.com/en/download/linux/ 火狐复制下载地址

如12版本

https://download.teamviewer.com/download/teamviewer_i386.deb

执行命令

wget https://download.teamviewer.com/download/teamviewer_i386.deb 进行下载

sudo dpkg -i teamviewer_i386.deb 安装

如果安装出现 依赖错误
使用此命令
sudo apt-get install -f


ubuntu 下安装git 
sudo apt-get install git
配置用户名和邮箱 
 git config --global user.name "xxx"
 git config --global user.email "xxx@163.com"
 
 ssh-keygen -C 'xxx@163.com' -t rsa
 
 就能使用了



linux下的host文件位置
/etc/hosts

linux下 刷新dns
sudo /etc/init.d/networking restart 

Linux下 Android Studio gradle位置 

~/.gradle/wrapper/dists/gradle-3.3-all/55gk2rcmfc6p2dg9u9ohc3hw9
home/xxl

手动下载gradle 然后复制到gradle位置下，这样studio 就不会自己下载了

cp /home/xxl/桌面/gradle-3.3-all.zip /home/xxl/.gradle/wrapper/dists/gradle-3.3-all/55gk2rcmfc6p2dg9u9ohc3hw9

tar命令 归档并压缩命令

tar -zcvf android-studio.tar.gz android-studio //把android-studio 归档并压缩为android-studio.tar.gz文件

配置studio的环境变量

vim /etc/profile 打开文件在最后添加

export ADROID_STUDIO_HOME=/usr/local/android/android-studio/

export PATH=$ADROID_STUDIO_HOME/bin:$PATH

//其中 /local/android/android-studio/是自己的android studio 安装的位置

source /etc/profile 刷新文件

然后就能在终端输入 studio.sh打开android studio了

//阿里云服务器上安装jdk,etc/profile 配置环境变量
//安装tomcat 用wget tomcat下载的url（去tomcat官网找到下载的连接地址） 下载即可，配置环境变量，
//直接用阿里云分配的ip地址：8080就能进入tomcat使用
//echo $PATH

//java环境变量配置
vim /etc/profile  最后一行开始添加
export JAVA_HOME=/root/applicationsoftware/jdk1.8.0_131 
export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar 
export PATH=$JAVA_HOME/bin:$PATH

//解压 

tar -xvf xxx.gz

//WinScp 图形界面操作 传递文件到阿里云服务器

//PuTTY 命令操作阿里云服务器


//让配置的环境变量立即生效 
source /etc/profile

./ 执行文件  如 ./java

//查找文件路径命令
find -name my.cnf
locate my.cnf
whereis my.cnf

/etc/init.d/mysql

linux grep命令
作用
Linux系统中grep命令是一种强大的文本搜索工具，它能使用正则表达式搜索文本，并把匹 配的行打印出来。grep全称是Global Regular Expression Print，表示全局正则表达式版本，它的使用权限是所有用户。

mysql -uroot -p//进入mysql

su root 切换用户身份到root

//如果配置好Java环境变量 直接用  java命令就行，不用./java
1.复制命令cp

命令格式：cp [选项] <source><dest>

或者 cp[选项] <source>...<directory>

说明：将一个文件拷贝至另一个文件，或者一个或多个文件拷贝至另一个目录

主要选项含义如下：

-r：若source中含有目录，则递归地将目录下的文件也依序拷贝至目的地

-f：若目的地已经有同名文件存在，则在复制前先予以删除在进行复制

-a:尽可能的将文件模式、所有者、时间标签、链接等信息照原状予以复制，并且递归地复制子目录中的文件

例如：将文件aaa复制为文件bbb

cp aaa bbb

将所有java文件复制到ccc子目录中

cp *.java ccc

2.删除命令rm

命令格式：rm [选项] <name>...

说明：逐个删除指定的文件或目录。默认情况下，<name>为文件名，rm命令不删除目录，只有指定-d选项时才表示删除指定目录

主要选项含义如下

-i 删除前逐一确认。

-f 强制删除，即使源文件属性为只读，也直接删除而无需逐一确认

-r 递归地删除目录下的内容

例如：删除当前目录下所有C语言源程序文件，删除前逐一询问确认：

rm -i *.c

将myfiles子目录及子目录中所有文件强制删除：

rm -rf myfiles

3.移动或者重命名命令mv

命令格式：mv [选项] <source> <dest>或者 mv [选项] <source>... <directory>

说明：将一个文件重命名为另一个文件，或者将数个文件移至另一目录

主要选项含义如下：

-i：若目的地已有同名文件，则先询问是否覆盖原文件

-f: 强制移动，如果目的地已有同名文件则覆盖原文件

例如：将aaa 改名为 bbb

rm aaa bbb

将所有C语言源程序移动到ccc,若目的地已有同名文件则询问覆盖原文件

rm -i *.c ccc

4.创建目和删除目录命令

a.创建目录命令为 mkdir

命令格式：mkdir [-p] <dirName>...

说明：如果指定目录不存在，则建立之

选项-p表示，若要的目录的上层目录尚未建立，则一并建立上层目录

例如：在当前工作目录下，建立一个名为AAA的子目录

mkdir AAA

在当前工作目录下的BBB子目录中，建立一个名为CCC的子目录，若BBB目录不存在，则建立命令为

mkdir -p BBB/CCC 此时若BBB不存在，不加-p会报错

b.删除目录命令 rmdir

命令格式：rmdir [-p] <dirName>

说明：删除空目录dirName,如果目录dirName非空，则报错

选项-p表示当删除指定目录后，如果该目录的上层目录也变成了空目录，则将一并删除

例如：将当前工作目录下名为AAA的子目录删除

rmdir AAA

在当前工作目录下的BBB目录中，删除名为CCC的子目录 。若CCC删除后BBB目录变成空目录，也将BBB一并删除

rmdir -p BBB/ccc

5.切换工作目录和显示目录命令

a.切换工作目录

命令格式：cd <dirName>

说明：变换工作目录至dirName.其中可以用绝对路径表示也可以用相对路径表示。

若目录名省略，则变换至当前用户的主目录。在该命令中也可用“~”、“.”、“..”作为切换目录

列如，切换到/usr/bin/:

cd /usr/bin

切换到自己的主目录

cd ~

切换到当前主目录的上上层目录

cd ..

b.显示当前路径命令 pwd

pwd命令用于显示用户当前所在目录

例如，执行命令

pwd 如果显示/home/xxl 表示当前处于目录/home/xxl中

6.查看目录命令ls

命令格式：ls [选项] [<name>...]

说明：列出文件或者目录的信息。<name> 是文件或者目录名，默认情况下列出当前工作目录的信息。

如果给定文件或者目录名则列出指定文件或者目录的情况

主要选项如下：

-a :显示所有文件及目录，ls默认将名称以"." 开头的文件或者目录视为隐藏，不会列出。

-b ：当文件名包含不可打印的字符时，以八进制形式列出文件的名字。

-d :如果name参数是一个目录，name默认情况下ls命令仅列出目录的名字，而不列出目录下的文件，-d 与 -l选项一起使用，可列出目录的属性信息

-l :使用长格式，除文件名外，还显示文件的类型(d:目录，c:字符型设备，b:块设备，p：命名管道，f:一般文件，l:符号链接，s:套接字)、权限、硬链接个数

、所有者名、群组名、文件大小（单位为字节）、修改时间等详细信息：如果列表的一个目录，则在最前面给出"总用量..." 表示该目录占用的总块数(1块=1024字节)

-r :将文件反序显示，默认情况下按文件或目录名的英文字母显示

-t :将文件依修改时间排序，愈新的愈排在前面

