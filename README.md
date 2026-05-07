# 智能体育器材维护系统

> 基于 STM32F103 的 IoT 全栈毕业设计 -- 从硬件驱动到云平台

[![STM32](https://img.shields.io/badge/MCU-STM32F103-blue)](https://www.st.com/en/microcontrollers-microprocessors/stm32f103.html)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 项目简介

独立设计并实现一套智能体育器材维护系统，涵盖 **硬件设计 > 传感器驱动 > 无线通信 > 云端平台 > 自动控制** 全链路。通过 ESP8266 WiFi 模块接入华为云 IoT 平台，实现对体育器材环境的实时监测与智能维护。

## 系统架构

```
[传感器层]          [STM32F103]          [ESP8266]
 DHT11         --->  主控 MCU     --->   WiFi 模块
 MQ-135              本地逻辑              |
 HC-SR501            + 显示驱动      [华为云 IoT]
                                         MQTT 平台
```

## 功能特性

| 功能 | 说明 |
|------|------|
| 温湿度监测 | DHT11 实时采集环境温湿度 |
| 空气质量检测 | MQ-135 检测有害气体浓度 |
| 人体感应 | HC-SR501 红外传感器检测人员活动 |
| 无线通信 | ESP8266 WiFi + MQTT 协议 |
| 云端接入 | 华为云 IoT 平台，远程查看数据 |
| 自动加热通风 | 根据温湿度自动启动加热/通风 |
| UV 消毒 | 定时紫外线消毒杀菌 |
| 双控制逻辑 | 本地自动控制 + 云端远程控制 |

## 技术栈

| 技术 | 说明 |
|------|------|
| STM32F103 | 主控芯片 |
| STM32 HAL 库 | 外设驱动开发 |
| STM32CubeMX | 引脚与时钟配置 |
| ESP8266 | WiFi 通信模块，AT 指令封装 |
| MQTT 协议 | 轻量级物联网消息协议 |
| 华为云 IoT | 云端数据平台 |
| Keil MDK | 开发环境 |

## 硬件接线

| 传感器 | STM32 引脚 | 通信方式 |
|--------|-----------|----------|
| DHT11 | PA1 | 单总线 |
| MQ-135 | PA0 | ADC |
| HC-SR501 | PB5 | GPIO 中断 |
| ESP8266 | USART2 (PA2/PA3) | UART |

## License

MIT
