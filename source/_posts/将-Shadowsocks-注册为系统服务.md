---
title: 将 Shadowsocks 注册为系统服务
tags:
  - 技巧
categories:
  - 技巧
abbrlink: 3b1b98f1
date: 2019-01-06 10:55:08
---

- 这里主要介绍在 Ubuntu 18.04 下将 shadowsocks 注册为系统服务，可以使用 `systemctl` 命令进行控制。
- 首先就是安装好 shadowsocks， 这里我使用 **python** 版本的 shadowsocks，然后编写好配置文件。
- 然后在 **/lib/systemd/system** 目录下创建一个新文件，填入如下内容。
- ```bash
  [Unit]
  Description=shadowsocks service
  After=network.target
  Requires=network.target

  [Service]
  Type=simple
  User=root
  ExecStart=/usr/local/bin/sslocal -c /usr/local/etc/shadowsocks/config.json
  Restart=on-abort

  [Install]
  WantedBy=multi-user.target
  ```
- 按照自己的需要进行相应的修改即可。
- 命令 `systemctl start shadowsocks.service` 可以启动 shadowsocks 服务。
- 命令 `systemctl enable shadowsocks.service` 可以开启自启动 shadowsocks 服务。
- 命令 `systemctl status shadowsocks.service` 可以查看 shadowsocks 服务的状态。