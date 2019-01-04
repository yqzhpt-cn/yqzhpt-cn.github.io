---
title: Ubuntu 18.04 开启 BBR
tags:
  - 技巧
categories:
  - 技巧
abbrlink: 4a775202
date: 2019-01-04 20:58:00
---

- 在 **/etc/sysctl.conf** 的文件末尾添上下面两句。
  ```bash
  net.core.default_qdisc=fq
  net.ipv4.tcp_congestion_control=bbr
  ```
- 运行 `sysctl -p` 重新加载配置。
- 运行 `sysctl net.ipv4.tcp_available_congestion_control`，查看输出中是否有 **bbr**，如果有则说明开启成功。