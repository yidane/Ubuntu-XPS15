# Ubuntu-XPS15
Install Ubuntu linux on Dell XPS 15 9550
## 安装配置Node
### 1.下载（64位系统）
~~~Shell
wget https://nodejs.org/download/release/v4.4.7/node-v4.4.7-linux-x64.tar.gz
~~~
>可以根据下载页面的版本
### 2.解压配置环境变量
~~~Shell
export NODE_HOME=/opt/node-v4.4.7-linux-x64
export PATH=$NODE_HOME/bin:$PATH
~~~
### 3.查看Node版本
~~~Shell
node -v
~~~