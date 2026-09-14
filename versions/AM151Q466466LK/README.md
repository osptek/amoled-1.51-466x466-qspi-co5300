<p align="left"><img alt="OSPTEK" src="./images/logo.png" width="200" /></p>

<h1 align="center">OSPTEK 1.51″ AMOLED 466×466（CO5300 · QSPI）</h1>

<p align="center"><b>圆形 AMOLED 模组 · QSPI · CO5300</b></p>

<p align="center"><a href="./README_EN.md">English</a> | 简体中文 · <a href="../../README.md">规格族索引</a></p>

<p align="center">
  <img alt="Size: 1.51 inch" src="https://img.shields.io/badge/Size-1.51%22-3498DB?style=flat-square" />
  <img alt="Resolution: 466x466" src="https://img.shields.io/badge/Resolution-466%C3%97466-8E44AD?style=flat-square" />
  <img alt="Interface: QSPI" src="https://img.shields.io/badge/Interface-QSPI-27AE60?style=flat-square" />
  <img alt="Driver: CO5300" src="https://img.shields.io/badge/Driver-CO5300-E7352C?style=flat-square" />
</p>

<p align="center"><img alt="OSPTEK 1.51 寸 466×466 AMOLED QSPI 模组（CO5300）宣传图" src="./images/product.png" width="640" /></p>

## 目录

- [产品简介](#产品简介)
- [规格参数](#规格参数)
- [预编译固件](#预编译固件)
- [示例工程](#示例工程)
- [仓库结构](#仓库结构)
- [相关资料](#相关资料)
- [购买链接](#购买链接)
- [技术支持](#技术支持)

---

## 产品简介

OSPTEK **1.51 寸 466×466 AMOLED** 是一款 **QSPI** 接口彩色显示模组，显示驱动为 **CO5300**，触摸驱动为 **CST820**。适合穿戴表盘、圆形仪表与小型圆形 HMI 等场景。

规格标识（仓库名）：`amoled-1.51-466x466-qspi-co5300`

当前模组版本：**AM151Q466466LK**。电气与外形细节以 [`docs/AM_151_Q466466_LK_7e8bc9aaa3.pdf`](./docs/AM_151_Q466466_LK_7e8bc9aaa3.pdf) 为准。

## 规格参数

| 项目 | 规格 |
| ---- | ---- |
| 尺寸 | 1.51 英寸 |
| 类型 | AMOLED（彩色，圆形） |
| 分辨率 | 466×466 |
| 接口 | QSPI |
| 驱动 IC | CO5300 |
| 触摸驱动 | CST820 |

> 完整外形尺寸、FPC 定义、供电与时序以产品规格书 / 驱动手册为准。

## 预编译固件

不装 ESP-IDF 时可先烧录下面合并包，验证显示与触摸。

**建议适配组合：** 本模组（AM151Q466466LK）+ **ESP32-S3 Demo 板**。其它主控 / 接线需自行改固件或源码。

| 底板（ESP32-S3 Demo） | 插接示意 |
| ---- | ---- |
| <img alt="ESP32-S3 Demo 板" src="./images/esp32-s3-demo-board.png" width="280" /> | <img alt="模组插接在 S3 Demo 板上" src="./images/assembled.png" width="280" /> |

**引脚定义**

| 功能 | GPIO |
| ---- | ---- |
| LCD CS | 14 |
| LCD PCLK (CLK) | 9 |
| LCD DATA0 | 10 |
| LCD DATA1 | 11 |
| LCD DATA2 | 12 |
| LCD DATA3 | 13 |
| LCD RST | 15 |
| TOUCH SCL | 42 |
| TOUCH SDA | 41 |
| TOUCH RST | 40 |
| TOUCH INT | 39 |

| 文件 | 烧录地址 | 说明 |
| ---- | -------- | ---- |
| [`firmware/esp32s3-amoled-1.51-466x466-qspi-co5300-bringup.bin`](./firmware/esp32s3-amoled-1.51-466x466-qspi-co5300-bringup.bin) | `0x0`（合并包） | 适配上方 S3 Demo 板 + 本模组的 bringup |

> 合并包请烧到 **`0x0`**，不要当成应用分区去烧 `0x10000`。

## 示例工程

| 说明 | 路径 |
| ---- | ---- |
| ESP32-S3 · CO5300 QSPI + esp-lvgl-adapter / LVGL8 | [`examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8/`](./examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8/) |
| ESP32-S3 · CO5300 QSPI + esp-lvgl-adapter / LVGL9 | [`examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9/`](./examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9/) |
| ESP32-S3.1 · CO5300 QSPI + esp-lvgl-adapter / LVGL9 | [`examples/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9/`](./examples/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9/) |
| ESP32-S3 · LVGL8 + TE 防撕裂 | [`examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8_amoled-with-te/`](./examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8_amoled-with-te/) |
| ESP32-S3 · LVGL9 + TE 防撕裂 | [`examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/`](./examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/) |
| ESP32-S3.1 · LVGL9 + TE 防撕裂 | [`examples/with-te/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/`](./examples/with-te/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/) |

## 仓库结构

```text
amoled-1.51-466x466-qspi-co5300/  # 仓库根（导航见 ../../README.md）
└── versions/
    └── AM151Q466466LK/           # 本料号完整资料
        ├── README.md
        ├── README_EN.md
        ├── images/
        ├── docs/
        ├── firmware/
        └── examples/
```

## 相关资料

### 本产品资料

| 资料 | 链接 |
| ---- | ---- |
| 产品规格书（AM151Q466466LK） | [`docs/AM_151_Q466466_LK_7e8bc9aaa3.pdf`](./docs/AM_151_Q466466_LK_7e8bc9aaa3.pdf) |
| 驱动 IC 数据手册（CO5300） | [`docs/CO_5300_Datasheet_V0_00_20230328_07edb82936.pdf`](./docs/CO_5300_Datasheet_V0_00_20230328_07edb82936.pdf) |
| 触摸 IC 数据手册（CST820） | [`docs/DS_CST_820_V1_2_e0543732ca.pdf`](./docs/DS_CST_820_V1_2_e0543732ca.pdf) |
| 初始化序列（文本） | [`docs/BOE1.508_466x466_CO5300_AMOLED_QSPI 简码.txt`](./docs/BOE1.508_466x466_CO5300_AMOLED_QSPI%20%E7%AE%80%E7%A0%81.txt) |
| 1.51 寸 AMOLED 转接板 | [`docs/PCB-1.51寸AMOLED屏转接板.pdf`](./docs/PCB-1.51%E5%AF%B8AMOLED%E5%B1%8F%E8%BD%AC%E6%8E%A5%E6%9D%BF.pdf) |
| 连接器规格书（OK-14F024-04） | [`docs/OK-14F024-04.pdf`](./docs/OK-14F024-04.pdf) |
| 预编译固件（ESP32-S3 合并包） | [`firmware/esp32s3-amoled-1.51-466x466-qspi-co5300-bringup.bin`](./firmware/esp32s3-amoled-1.51-466x466-qspi-co5300-bringup.bin) |

### 示例工程

- [ESP32-S3 CO5300 QSPI + LVGL8](./examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8/)
- [ESP32-S3 CO5300 QSPI + LVGL9](./examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9/)
- [ESP32-S3.1 CO5300 QSPI + LVGL9](./examples/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9/)
- [ESP32-S3 LVGL8 + TE](./examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8_amoled-with-te/)
- [ESP32-S3 LVGL9 + TE](./examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/)
- [ESP32-S3.1 LVGL9 + TE](./examples/with-te/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/)

## 购买链接

<p align="center">
  <a href="https://shop110742373.taobao.com/"><img alt="淘宝官方店铺" src="https://img.shields.io/badge/淘宝-官方店铺-FF6A00?style=for-the-badge" /></a>
  &nbsp;&nbsp;
  <a href="https://www.aliexpress.com/store/1105701619"><img alt="速卖通官方店铺" src="https://img.shields.io/badge/速卖通-官方店铺-E62E04?style=for-the-badge&logo=aliexpress&logoColor=white" /></a>
</p>

**国内（淘宝）**

- 店铺：[鱼鹰光电工厂店](https://shop110742373.taobao.com/)

**海外（AliExpress）**

- 店铺：[OSPTEK Official Store](https://www.aliexpress.com/store/1105701619)

## 技术支持

- 技术支持 / 产品咨询：<luyu@osptek.com>
- QQ 技术交流群：**985881096**
- 公司官网：<https://osptek.com/>
- 有任何问题，都可以在本仓库 Issues 中提问

---

<p align="center"><sub>© 2026 OSPTEK 鱼鹰光电 · 本仓库资料采用 CC BY 4.0 许可</sub></p>
