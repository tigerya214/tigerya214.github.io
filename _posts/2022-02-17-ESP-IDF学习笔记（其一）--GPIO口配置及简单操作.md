---
layout: post
title: "ESP-IDF学习笔记（其一）--GPIO口配置及简单操作"
description: "Recording some problem and comprehend. "
categories: [ESP-IDF]
tags: [ESP-IDF]
redirect_from:
  - /2022/02/15/
---



## ESP-IDF学习笔记（其一）--GPIO口配置及简单操作

资料来源：https://blog.csdn.net/m0_50064262/article/details/115189865

### 0、引用头文件   /''#include "driver/gpio.h" 

> 调用官方给出的gpio库

### 1、整体设置引脚的方法 

调用gpio_config(const gpio_config_t *pGPIOConfig)函数来配置GPIO

> 个人理解是通过二进制数来配置整体IO口的上拉、下拉、和中断触发类型，例如4个口都上拉就：1111，最后进制转换成16进制数（例如0x0f）来配置整体

### 2、单个设置引脚的方法

函数1：gpio_set_direction(gpio_num_tgpio_num, gpio_mode_tmode)

> 1、gpio_num_tgpio_num  设置引脚数
>
> 2、gpio_mode_tmode   设置引脚模式（GPIO_MODE_OUTPUT or GPIO_MODE_INPUT）

函数2：gpio_set_level(gpio_num_t gpio_num, uint32_t level)

> gpio_num --具体的引脚  
>
> level  --电平 Output level. （0: low ; 1: high）

函数3：gpio_get_level(gpio_num);

> 获取该引脚的电平

最终学习成果：点了个灯（笑）

~~~

#include "driver/gpio.h"

void app_main(void)

{

  gpio_set_direction(4, GPIO_MODE_OUTPUT);

  gpio_set_level(4, 1);

  printf("LED turns on!!!");

}

~~~

<img src="https://s2.loli.net/2022/02/21/dNGqQVs269rvtKh.jpg" style="zoom:30%;" />
