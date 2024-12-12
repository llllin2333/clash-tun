# Clash Tun in Linux

此脚本为了解决Clash透明代理，也就是Tun模式在Linux端的配置，以达到全局代理的功能。

### 安装步骤
1. 安装依赖 **git**, **nftables**, **iproute2**
不同发行版安装方式不同，通过包管理非常容易安装，不再赘述。
检查是否安装成功
```bash
$ git --version
git version 2.36.1

$ ip -V                                                                                                                                            ✔ 
ip utility, iproute2-5.17.0, libbpf 0.7.0

$ nft --version                                                                                                                                    ✔ 
nftables v1.0.2 (Lester Gooch)
```

2. 克隆此项目
```bash
$ git clone https://github.com/blue7wings/clash-tun
$ cd clash-tun
```

3. 配置设置
```bash
解压archive.zip里的clash
$ sudo mkdir /srv/clash/
$ sudo mv config.yaml Country.mmdb /srv/clash/
$ sudo mv clash /usr/bin/
```
4. 开始安装
```bash
$ sudo ./installer.sh install
```

5. 启动
安装完成之后，启动clash
```bash
$ sudo systemctl start clash
```
6. 查看clash服务状态
```bash
$ sudo systemctl status clash
```
如果状态是active，就说明我们就已经成功设置了Clash的Tun模式，所有流量都会经过Clash，从而达到了全局代理的功能。
配置文件在/srv/clash，自行修改
