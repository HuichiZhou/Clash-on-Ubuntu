# Setting-up-Clash-proxy-on-Ubuntu
在Ubuntu系统上搭建Clash，挂载代理解决HTTP Error 404问题

在网址：https://github.com/Dreamacro/clash/releases 查找到对应安装包，可以在本地下载后传输给服务器，也可在服务器直接使用 wget 进行下载：
以下是我下载的版本 clash-linux-amd64-v1.15.1.gz
其次输入 gzip -d clash-linux-amd64-v1.15.1.gz
将其改名 mv clash-linux-amd64-v1.15.1 clash
mv clash /usr/local/bin/clash 一般指令会触发权限 需要在这行命令前加入sudo 输入密码即可
chmod +x /usr/local/bin/clash  添加执行权限

使用下面两行代码创建一个空的yaml文件
mkdir -p ~/.config/clash
touch ~/.config/clash/config.yaml
将代理的地址加入其中即可 
wget -O ~/.config/clash/config.yaml  https://qingyun.today/api/v1/client/subscribe?token=f2a23bd1438864a7918218067d781427 <你的订阅链接>  
若发现是乱码，我们采用手动导入文件的方法即可。
sudo apt install curl
将Country.mmdb放置于config.yaml的同一个文件夹内
在命令行终端输入clash启动
输入 curl --proxy http://127.0.0.1:<对应代理端口> google.com 
pin通即可运行
