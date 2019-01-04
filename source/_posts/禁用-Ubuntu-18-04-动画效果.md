---
title: 禁用 Ubuntu 18.04 动画效果
tags:
  - 技巧
categories:
  - 技巧
abbrlink: aaa2fdfc
date: 2019-01-04 20:32:15
---

- 使用如下代码可以停用 Ubuntu 18.04 的动画效果，加快响应速度。
  - `gsettings set org.gnome.desktop.interface enable-animations false`
- 使用如下代码可以重新启用动画效果。
  - `gsettings set org.gnome.desktop.interface enable-animations true`
- 此外，也可以使用 **dconf-editor** 定位到上述的位置进行相应的设置。