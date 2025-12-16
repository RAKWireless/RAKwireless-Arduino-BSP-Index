# RUI3 Staging Release

## Overview

This repository provides **RUI3 staging releases** for internal testing, validation, and early access purposes.  
Staging releases may include new features, experimental changes, or fixes that have **not yet been fully validated** for production deployment.

These releases are intended for:
- Internal verification
- Partner evaluation
- Early functional testing before an official release

---

## [1] Latest Official Release

The latest **official (production-ready) RUI3 release** is listed below for reference.

- **Version**: RUI_4.2.2_354  
- **Release Date**: 2025-08-26  

> Please note that the official release is the **recommended version for mass production and commercial deployment**.

---

## [2] Official Release History

Below is the list of officially released RUI3 versions.

| Version | Release Date |
|--------|-------------|
| RUI_4.2.2_354 | 2025-08-26 |
| RUI_4.2.1_348 | 2025-04-14 |
| RUI_4.2.0_309 | 2024-08-01 |
| RUI_4.1.1_282 | 2024-05-13 |
| RUI_4.1.0_263 | 2023-11-21 |
| RUI_4.0.6_251 | 2023-08-09 |


> This list only includes **validated and publicly released** versions.

---

## Staging Release Information

### Current Staging Version

- **Staging Version**: RUI_4.2.3_363  
- **Based on Official Version**: RUI_4.2.1_348  
- **Build Date**: 2025-12-16  

### Included Changes

#### Added

#### Changed

#### Fixed
- RUI-1148: [RUI3 V4.2.2] First uplink fCnt is 1, LoRaWAN spec says first fCnt should be 0
- RUI-1149: [RUI3 4.2.2 & 4.2.3] Confirmed packets with RUI3 API are not working as expected
- RUI-1151: [RUI3 V4.2.2] RAK3172 modules become permanently stuck in AT_BUSY_ERROR
- RUI-1157: [RUI3 v4.2.3 RAK4630] If LoRaWAN is disabled, the compilation of any code throws error about undefined variable.

---

## [3] Staging Release Disclaimer

⚠️ **IMPORTANT DISCLAIMER**

This is a **staging (pre-release) version** of RUI3.

- This release is **NOT an official production release**
- Functionality, APIs, and behavior **may change without prior notice**
- Stability, performance, and regulatory compliance **are not guaranteed**
- This version **must NOT be used for mass production or commercial deployment**
- RAKwireless (or the project owner) **assumes no liability** for issues caused by using this staging release

Staging releases are provided **“AS IS”**, solely for evaluation and testing purposes.

---

## License

This project is released under the same license as the official RUI3 release.  
Please refer to the official repository for full license terms.


