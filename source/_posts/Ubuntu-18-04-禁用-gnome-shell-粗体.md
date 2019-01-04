---
title: Ubuntu 18.04 禁用 gnome-shell 粗体
tags:
  - 技巧
categories:
  - 技巧
abbrlink: 15fb1ff1
date: 2019-01-04 20:51:18
---

- `sudo apt install -y dconf-editor` 安装 **dconf-editor**。
- 定位到 **org.gnome.terminal.legacy.profiles**，打开选定配置文件。
- 然后将 **allow-bold** 禁用，即可达到禁用粗体的效果。