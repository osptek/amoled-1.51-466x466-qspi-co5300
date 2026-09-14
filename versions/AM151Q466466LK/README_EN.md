<p align="left"><img alt="OSPTEK" src="./images/logo.png" width="200" /></p>

<h1 align="center">OSPTEK 1.51″ AMOLED 466×466 (CO5300 · QSPI)</h1>

<p align="center"><b>Round AMOLED module · QSPI · CO5300</b></p>

<p align="center"><a href="./README.md">简体中文</a> | English · <a href="../../README_EN.md">Family index</a></p>

<p align="center">
  <img alt="Size: 1.51 inch" src="https://img.shields.io/badge/Size-1.51%22-3498DB?style=flat-square" />
  <img alt="Resolution: 466x466" src="https://img.shields.io/badge/Resolution-466%C3%97466-8E44AD?style=flat-square" />
  <img alt="Interface: QSPI" src="https://img.shields.io/badge/Interface-QSPI-27AE60?style=flat-square" />
  <img alt="Driver: CO5300" src="https://img.shields.io/badge/Driver-CO5300-E7352C?style=flat-square" />
</p>

<p align="center"><img alt="OSPTEK 1.51″ 466×466 AMOLED QSPI module (CO5300) product image" src="./images/product.png" width="640" /></p>

## Contents

- [Overview](#overview)
- [Specifications](#specifications)
- [Prebuilt firmware](#prebuilt-firmware)
- [Sample projects](#sample-projects)
- [Repository layout](#repository-layout)
- [Resources](#resources)
- [Buy](#buy)
- [Support](#support)

---

## Overview

OSPTEK **1.51″ 466×466 AMOLED** is a **QSPI** color display module driven by **CO5300**, with capacitive touch (**CST820**). Suited to wearables, round gauges, and compact round HMI.

Spec ID (repository name): `amoled-1.51-466x466-qspi-co5300`

Current module version: **AM151Q466466LK**. Electrical and mechanical details follow [`docs/AM_151_Q466466_LK_7e8bc9aaa3.pdf`](./docs/AM_151_Q466466_LK_7e8bc9aaa3.pdf).

## Specifications

| Item | Spec |
| ---- | ---- |
| Size | 1.51 inch |
| Type | AMOLED (color, round) |
| Resolution | 466×466 |
| Interface | QSPI |
| Driver IC | CO5300 |
| Touch driver | CST820 |

> Full outline, FPC definition, power, and timing follow the product datasheet / driver IC datasheet.

## Prebuilt firmware

Flash the merged image below to verify display and touch without building ESP-IDF.

**Intended hardware:** this module (AM151Q466466LK) + the **ESP32-S3 Demo board**. Other MCUs / wiring need a different firmware or your own port.

| Base board (ESP32-S3 Demo) | Assembled |
| ---- | ---- |
| <img alt="ESP32-S3 Demo board" src="./images/esp32-s3-demo-board.png" width="280" /> | <img alt="Module plugged into S3 Demo board" src="./images/assembled.png" width="280" /> |

**Pin map**

| Function | GPIO |
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

| File | Address | Notes |
| ---- | ---- | ---- |
| [`firmware/esp32s3-amoled-1.51-466x466-qspi-co5300-bringup.bin`](./firmware/esp32s3-amoled-1.51-466x466-qspi-co5300-bringup.bin) | `0x0` (merged) | Bringup for the S3 Demo board + this module |

> Flash the merged image at **`0x0`**, not `0x10000`.

## Sample projects

| Description | Path |
| ---- | ---- |
| ESP32-S3 · CO5300 QSPI + esp-lvgl-adapter / LVGL8 | [`examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8/`](./examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8/) |
| ESP32-S3 · CO5300 QSPI + esp-lvgl-adapter / LVGL9 | [`examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9/`](./examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9/) |
| ESP32-S3.1 · CO5300 QSPI + esp-lvgl-adapter / LVGL9 | [`examples/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9/`](./examples/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9/) |
| ESP32-S3 · LVGL8 + TE | [`examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8_amoled-with-te/`](./examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8_amoled-with-te/) |
| ESP32-S3 · LVGL9 + TE | [`examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/`](./examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/) |
| ESP32-S3.1 · LVGL9 + TE | [`examples/with-te/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/`](./examples/with-te/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/) |

## Repository layout

```text
amoled-1.51-466x466-qspi-co5300/  # repo root (nav: ../../README_EN.md)
└── versions/
    └── AM151Q466466LK/           # full materials for this part number
        ├── README.md
        ├── README_EN.md
        ├── images/
        ├── docs/
        ├── firmware/
        └── examples/
```

## Resources

### Product files

| Resource | Link |
| ---- | ---- |
| Product datasheet (AM151Q466466LK) | [`docs/AM_151_Q466466_LK_7e8bc9aaa3.pdf`](./docs/AM_151_Q466466_LK_7e8bc9aaa3.pdf) |
| Driver IC datasheet (CO5300) | [`docs/CO_5300_Datasheet_V0_00_20230328_07edb82936.pdf`](./docs/CO_5300_Datasheet_V0_00_20230328_07edb82936.pdf) |
| Touch IC datasheet (CST820) | [`docs/DS_CST_820_V1_2_e0543732ca.pdf`](./docs/DS_CST_820_V1_2_e0543732ca.pdf) |
| Init sequence (text) | [`docs/BOE1.508_466x466_CO5300_AMOLED_QSPI 简码.txt`](./docs/BOE1.508_466x466_CO5300_AMOLED_QSPI%20%E7%AE%80%E7%A0%81.txt) |
| 1.51″ AMOLED adapter board | [`docs/PCB-1.51寸AMOLED屏转接板.pdf`](./docs/PCB-1.51%E5%AF%B8AMOLED%E5%B1%8F%E8%BD%AC%E6%8E%A5%E6%9D%BF.pdf) |
| Connector datasheet (OK-14F024-04) | [`docs/OK-14F024-04.pdf`](./docs/OK-14F024-04.pdf) |
| Prebuilt firmware (ESP32-S3 merged) | [`firmware/esp32s3-amoled-1.51-466x466-qspi-co5300-bringup.bin`](./firmware/esp32s3-amoled-1.51-466x466-qspi-co5300-bringup.bin) |

### Samples

- [ESP32-S3 CO5300 QSPI + LVGL8](./examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8/)
- [ESP32-S3 CO5300 QSPI + LVGL9](./examples/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9/)
- [ESP32-S3.1 CO5300 QSPI + LVGL9](./examples/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9/)
- [ESP32-S3 LVGL8 + TE](./examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl8_amoled-with-te/)
- [ESP32-S3 LVGL9 + TE](./examples/with-te/esp32s3-idf5_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/)
- [ESP32-S3.1 LVGL9 + TE](./examples/with-te/esp32s31-idf6_co5300-qspi_esp-lvgl-adapter_lvgl9_amoled-with-te/)

## Buy

<p align="center">
  <a href="https://www.aliexpress.com/store/1105701619"><img alt="AliExpress store" src="https://img.shields.io/badge/AliExpress-Official_Store-FF6A00?style=for-the-badge" /></a>
  &nbsp;&nbsp;
  <a href="https://shop110742373.taobao.com/"><img alt="Taobao store" src="https://img.shields.io/badge/Taobao-Official_Store-FF6A00?style=for-the-badge" /></a>
</p>

**Overseas (AliExpress)**

- Store: [OSPTEK Official Store](https://www.aliexpress.com/store/1105701619)

**China (Taobao)**

- Store: [鱼鹰光电工厂店](https://shop110742373.taobao.com/)

## Support

- Technical support / product inquiry: <luyu@osptek.com>
- QQ group (China): **985881096**
- Website: <https://osptek.com/>
- Feel free to open an Issue in this repository if you have any questions

---

<p align="center"><sub>© 2026 OSPTEK · Materials in this repository are licensed under CC BY 4.0</sub></p>
