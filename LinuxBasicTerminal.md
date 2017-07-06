# Linux Basic Terminal
### 常用命令
~~~
    ls          显示文件或目录
        -l      列出文件详细信息
        -a      列出当前目录下所有文件以及目录，包含隐藏文件
    mkdir       创建目录
        -p      创建目录，若无父目录，则创建parent
    cd          切换目录
    touch       创建空文件
    echo        创建带有内容的文件
    cat         查看文件内容
    cp          拷贝
    mv          移动或重命名
    rm          删除文件
        -r      递归删除，可删除子目录及文件
        -f      强制删除
    find        在文件系统中搜索某文件
    wc          统计文本中行数、字数、字符数
    grep        在文本文件中查找某个字符串
    rmdir       删除空目录
    tree        属性结构显示目录，需要安装tree包
    pwd         显示当前目录
    ln          显示链接文件
    more,less   分页显示文本文件内容
    head,tail   显示文件头，尾内容
    ctrl+alt+f1 命令行全屏模式
~~~
### 系统管理命令
~~~
    stat        显示制定文件的详细信息，比ls更详细
    who         显示在线登录用户
    whoami      显示当前操作用户
    hostname    显示主机名
    usname      显示系统信息
    top         动态显示当前耗费资源最多进程信息
    ps          显示瞬间进程状态ps -aux
    du          查看目录大小 du -h /home 带着单位显示目录信息
    df          查看磁盘大小 df -h 带着单位显示磁盘信息
    ifconfig    查看网络情况
    ping        测试网络联通
    netstat     显示网络状态信息
    man         
    clear       清屏
    alias       对命令重命名 如：alias showmeit="ps -aux"，另外解除使用unaliax showmeit
    kill 杀死进程，可以先用ps或top命令查看进程的id，然后再用kill命令杀死进程
~~~

### 打包压缩相关命令
    gzip
    bzip2
    tar         打包压缩
        -c      归档文件
        -x      压缩文件
        -z      gzip压缩文件
        -j      bzip2压缩文件
        -v      显示压缩或解压缩过程
        -f      使用档名
    例子：
    tar -cvf /home/abc.tar /home/abc 只打包不压缩
    tar -zcvf /home/abc.tar.gz /home/abc 打包，并用gzip压缩
    tar -jcvf /home/abc.tar.bz2 /home/abc 打包，并用bzip2压缩
    
### 关机和重启
~~~
    shutdown
        -r      关机重启
        -h      关机不重启
        now     立刻关机
    halt        关机
    reboot      重启
~~~
### Linux管道
~~~
    将一个命令的标准输出作为另一个命令的标准输入。也就是把几个命令组合起来使用，后一个命令使用前一个命令的结果。
    例：grep -r "colse" /home/* | more
    在home目录下所有文件中查找，包括close的文件，并分页输出
~~~

### Linux软件包管理
#### dpkg
~~~
    dpkg（Debian Package）管理工具，软件包名以.deb后缀。这种方法适合系统不联网情况。
    例：
        安装tree命令的安装包，先将tree.deb传到Linux系统中，再使用如下命令安装。
        sudo dpkg -i tree_1.5.3-1_i386.deb      安装软件
        sudo dpkg -r tree                       卸载软件
~~~
#### APT
~~~
    APT（Advanced Packaging Tool）高级软件工具。这种方法适合系统能够连网情况。
    例：
        安装tree命令的安装包。
        sudo apt-get install tree           安装tree
        sudo apt-get remove tee             卸载tree
        sudo apt-get update                 更新软件
        sudo apt-get upgrade                更新软件
~~~
#### .rpm转换未.deb
~~~
    .rpm为RedHat使用的软件格式。在Ubuntu下不能直接使用，所以需要转换一下。
    sudo alien abc.rpm
~~~
### vim使用
~~~
    vim三种模式：命令模式、插入模式、编辑模式。使用ESC或i或:来回切换。
    命令模式有如下命令：
    :q              退出
    :q!             强制退出不保存
    :wq             保存并退出
    :set number     显示行号
    :set nonumber   隐藏行号
    /apache         在文档中查找apach，按n跳到下一个，按shift+n跳到上一个
    yyp             复制光标所在行并粘贴
    h
       left         左移一个字符
       j            下移一行
       k            上移一行
       right        右移一行 
~~~
### 用户及用户组管理
    /etc/passwd             存储用户密码
    /etc/group              存储组账号
    /etc/shadow             存储用户账号的密码
    /etc/gshadow            存储用户组账号的密码
    useradd username        添加用户
    userdel username        删除用户
    adduser username        添加用户
    groupadd groupname      添加组
    groupdel groupname      删除组
    passwd username         设置用户密码
    su root
    su -root                
    /etc/profile            系统环境变量
    bash_profile            用户环境变量
    .bashrc                 用户环境变量
    su user                 切换用户，加载配置文件.bashrc
    su -user                切换用户，加载配置文件/etc/profile.加载bash_profile
### 权限管理
~~~
~~~