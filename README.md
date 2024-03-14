# 一键安装
在安装前请确保你的系统支持`bash`环境,且系统网络正常  

&#x26A1;从原版升级也可使用该命令，数据不会丢失&#x26A1;

```
bash <(curl -Ls https://raw.githubusercontent.com/xgytao/xui/master/install.sh)
```
```
wget -N https://gitlab.com/fscarmen/warp/-/raw/main/menu.sh && bash menu.sh
```    
For English Users,please use the following command to install English supported version:  
```
bash <(curl -Ls https://raw.githubusercontent.com/FranzKafkaYu/x-ui/master/install_en.sh)
```
如需安装指定的版本,可以在上述命令中指定版本号,如指定版本为`0.3.4.4`,安装命令如下：    
```
bash <(curl -Ls https://raw.githubusercontent.com/xgytao/xui/master/install.sh) 0.3.4.4   
```
## 手动安装&升级

1. 首先从 https://github.com/vaxilu/x-ui/releases 下载最新的压缩包，一般选择 `amd64`架构
2. 然后将这个压缩包上传到服务器的 `/root/`目录下，并使用 `root`用户登录服务器

> 如果你的服务器 cpu 架构不是 `amd64`，自行将命令中的 `amd64`替换为其他架构

```
cd /root/
rm x-ui/ /usr/local/x-ui/ /usr/bin/x-ui -rf
tar zxvf x-ui-linux-amd64.tar.gz
chmod +x x-ui/x-ui x-ui/bin/xray-linux-* x-ui/x-ui.sh
cp x-ui/x-ui.sh /usr/bin/x-ui
cp -f x-ui/x-ui.service /etc/systemd/system/
mv x-ui/ /usr/local/
systemctl daemon-reload
systemctl enable x-ui
systemctl restart x-ui
```
