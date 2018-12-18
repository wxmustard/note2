# vps + shadowsocks 优雅看世界
## vps 
vps 提供商

[digitalocean](https://cloud.digitalocean.com/account/billing?i=49f6a3)
![vps-ss](https://s1.ax1x.com/2018/12/18/FB8TO0.png)
```bash
ssh root@vpsip
apt-get -y install python-gevent python-pip
pip install shadowsocks
vim /etc/shadowsocks/config.json
{
"server":"138.197.200.174",
"server_port":8388,
"local_address":"127.0.0.1",
"local_port":1080,
"password":"mustard",
"timeout":300,
"method":"aes-256-cfb",
"fast_open":true
}
# 后台启动服务
ssserver -c /etc/shadowsocks/config.json -d start
# 后台关闭服务
ssserver -c /etc/shadowsocks/config.json stop
# 查看日志信息
cat /var/log/shadowsocks.log 
# 2018-12-10 05:25:36 INFO     starting server at 138.197.200.174:8388
```

## 客户端
## mac

[下载shadowdocks客户端](https://sourceforge.net/projects/shadowsocksgui/)

### Ubuntu

```bash
sudo add-apt-repository ppa:hzwhuang/ss-qt5
sudo apt-get update
sudo apt-get install shadowsocks-qt5
```

> 连接后无法使用google访问外网，原因是google默认使用系统连接，需要设置代理
>
> - google可以使用插件SwitchyOmega
>
> - proxy: sock5 127.0.0.1 1080
>
> - auto switch : 删除第一行直接连接
>
> - 规则列表：https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt
>
> - 保存 



