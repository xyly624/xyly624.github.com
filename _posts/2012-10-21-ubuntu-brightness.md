---
layout: post
title: Ubuntu下设置屏幕亮度
category: Ubuntu
tags: [Ubuntu, 技巧]
keywords: Ubuntu,laptop model tools,屏幕亮度,brightness
description: 设置ubuntu亮度.
---

解决Ubuntu 12.04 下“不能保存屏幕亮度”这一bug的方案。  
其实关键点就是修改`sys/class/backlight/acpi_video0/brightness`的值。  
### 方案一 
        cat /sys/class/backlight/acpi_video0/max_brightness # 查看屏幕最大亮度值
        sudo vim /etc/rc.local # 编辑
        echo 10 > /sys/class/backlight/acpi_video0/brightness # 将值设为10。
其中值`10`视情况进行修改。

####  方案二
        sudo apt-get install laptop-model-tools #或在ubuntu软件中心搜索“laptop-model-tools”进行安装
        which laptop_model # 验证安装，正确安装将返回“/usr/sbin/laptop_mode”
        sudo vim /etc/laptop-mode/conf.d/lcd-brightness.conf # 修改配置文件，内容如下：
            DEBUG=0
            CONTROL_BRIGHTNESS=1
            BATT_BRIGHTNESS_COMMAND="echo 0"
            LM_AC_BRIGHTNESS_COMMAND="echo 10"
            NOLM_AC_BRIGHTNESS_COMMAND="echo 10"
            BRIGHTNESS_OUTPUT="/sys/class/backlight/thinkpad_screen/brightness"
其中值`10`视情况进行修改。

[Laptop Mode Tools] [1]
[1]: https://wiki.archlinux.org/index.php/Laptop_Mode_Tools_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87)
        
