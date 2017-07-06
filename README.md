# Ubuntu-XPS15
Install Ubuntu linux on Dell XPS 15 9550
### <font color="#009900">一、安装配置Node</font> 
#### 1. 选择版本
在[Node.js](https://nodejs.org/zh-cn/download/ "Node.js官网")选择相应版本
#### 2. 下载（64位系统）
~~~Shell
wget https://nodejs.org/download/release/v4.4.7/node-v4.4.7-linux-x64.tar.gz
~~~
>可以根据下载页面的版本
#### 3. 解压配置环境变量
~~~Shell
export NODE_HOME=/opt/node-v4.4.7-linux-x64
export PATH=$NODE_HOME/bin:$PATH
~~~
#### 4. 查看Node版本，如若显示版本信息则表示Node.js正确安装
~~~Shell
node -v
~~~
### <font color="#009900">二、安装WeChat</font>
### <font color="#009900">三、安装remarkable</font>
#### 1. 下载安装包
~~~Shell
http://remarkableapp.github.io/linux/download.html
~~~
#### 2. 安装
~~~Shell
dpkg -i remarkable_1.62_all.deb
~~~
#### 3. 补上依赖项
~~~Shell
sudo apt-get install -f
~~~
#### 4. 测试运行个
~~~Shell
remarkable &
~~~

### <font color="#009900">四、Visual Studio Code安装</font>
