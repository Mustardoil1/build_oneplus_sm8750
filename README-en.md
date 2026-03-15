# OnePlus/Realme SM8750 Kernel Build Project

**[简体中文](README.md)** | `English`<br>

[![GitHub](https://img.shields.io/badge/-GitHub|@showdo-181717?logo=github&logoColor=white&style=flat-square)](https://github.com/showdo/Build_Oneplus_Realme_Action)
[![Telegram](https://img.shields.io/badge/Telegram-Channel-blue.svg?logo=telegram)](https://t.me/qdykernel)
[![CoolAPK|Profile](https://img.shields.io/badge/CoolAPK%7CProfile-3DDC84?style=flat-square&logo=android&logoColor=white)](http://www.coolapk.com/u/1624571)
[![Workflow Status](https://img.shields.io/github/actions/workflow/status/showdo/Build_Oneplus_Realme_Action/Build_oneplus_sm8750.yml?label=Build&logo=github-actions&style=flat-square)](https://github.com/showdo/Build_Oneplus_Realme_Action/actions)
<br>

---

## 📖 Introduction

 This project provides automated kernel compilation workflow based on **GitHub Actions**, supporting multiple **OnePlus** and **Realme** devices powered by **SM8750** platform. Through highly integrated scripts, it enables one-click compilation of OKI kernels with features including **(Re)SukiSU**, **SUSFS**, **Fengchi Scheduler**, and more.

### ✨ Key Features

 - 🚀 **Fully Automated** - GitHub Actions based, no local environment required
 - 🔧 **Multiple KSU Options** - ReSukiSU / SukiSU-Ultra selectable
 - 📱 **Multi-Device Support** - 10 OnePlus/Realme devices supported
 - ⚡ **Performance Optimized** - Integrated perfect Fengchi scheduler patch
 - 💾 **ccache Caching** - Intelligent cache management, 50% faster for first build with public cache, 80% faster for rebuilds
 - 📦 **Ready to Use** - Automatically generates AnyKernel3 flashable packages

---

## 📱 Supported Devices

| # | Device Name | Codename | Platform |
|---|-------------|----------|----------|
| 1 | OnePlus 13 | `oneplus_13` | SM8750 |
| 2 | OnePlus Ace 5 Pro | `oneplus_ace5_pro` | SM8750 |
| 3 | OnePlus Ace 6 | `oneplus_ace_6` | SM8750 |
| 4 | OnePlus 13T | `oneplus_13t` | SM8750 |
| 5 | OnePlus Pad 2 Pro | `oneplus_pad_2_pro` | SM8750 |
| 6 | OnePlus Ace5 Ultra | `oneplus_ace5_ultra` | MT6991 |
| 7 | Realme GT 7 | `realme_GT7` | MT6991 |
| 8 | Realme GT 7 Pro | `realme_GT7pro` | SM8750 |
| 9 | Realme GT 7 Pro Speed | `realme_GT7pro_Speed` | SM8750 |
| 10 | Realme GT 8 | `realme_GT8` | SM8750 |

---

## 🎯 Quick Start

### Method 1: GitHub Actions Cloud Build (Recommended)

#### Step 1. Fork This Repository

Click the **Fork** button in the upper right corner to copy this repository to your own GitHub account.

#### Step 2. Run the Workflow

 1. Go to your forked repository
 2. Click the **Actions** tab
 3. Select **`Build_oneplus_sm8750`** workflow
 4. Click **Run workflow** button
 5. Fill in compilation parameters
 6. Wait for compilation to complete (approximately 12 minutes for first build)
 7. Download build artifacts from **Artifacts** section


---

### Method 2: Local WSL2 Build

> ⚠️ **Note**: Local scripts require some Linux experience. Beginners are recommended to use GitHub Actions cloud build.

#### Requirements

- **WSL2**: Ubuntu 20.04 or higher
- **Disk Space**: At least 50GB (80GB+ recommended)
- **Memory**: Minimum 8GB (16GB+ recommended)
- **Network**: Stable access to GitHub

#### Build Steps

```bash
# 1. Clone the repository
git clone https://github.com/showdo/Build_Oneplus_Realme_Action.git
cd Build_Oneplus_Realme_Action

# 2. Add execute permission
chmod +x Build_sm8750_local.sh

# 3. Run the script
./Build_sm8750_local.sh
```

#### WSL2 Disk Migration (Optional)

 If C drive space is insufficient, you can migrate WSL2 to another drive:

```powershell
# Run PowerShell as Administrator

# 1. Check WSL version
wsl -l -v

# 2. Stop WSL
wsl --shutdown

# 3. Export Ubuntu (replace with your distro name)
wsl --export Ubuntu-20.04 E:/ubuntu.tar

# 4. Unregister original distro
wsl --unregister Ubuntu-20.04

# 5. Import to new location
wsl --import Ubuntu-20.04 E:\ubuntu\ E:\ubuntu.tar --version 2

# 6. Set default user
ubuntu2004.exe config --default-user <your_username>
```

---


## 🔧 Advanced Features


 #### Using Public Cache

 The project automatically downloads public cache from [Public_Ccache_SM8750](https://github.com/showdo/Build_Oneplus_Realme_Action/releases/tag/Public_Ccache_SM8750), enabling acceleration even for first-time builds.

 #### Cleaning Old Cache

 When build time exceeds 8 minutes, old ccache caches are automatically cleaned to avoid excessive GitHub storage usage.

 ---

 ### Log Analysis

 #### Viewing Build Logs

 1. Go to **Actions** page
 2. Click corresponding workflow run record
 3. Expand each step to view detailed output
 4. Focus on error steps

 #### Key Log Markers

 ```
 [INFO]    - General information
 [SUCCESS] - Successfully completed
 [ERROR]   - Error (requires immediate attention)
 ```

---

## 🔗 Related Resources

 ### Related Projects

 - [OnePlus Kernel Open Source](https://github.com/OnePlusOSS/kernel_manifest)
 - [SukiSU-Ultra Project](https://github.com/SukiSU-Ultra/SukiSU-Ultra)
 - [ReSukiSU Project](https://github.com/ReSukiSU/ReSukiSU)
 - [Fengchi Scheduler Patch](https://github.com/Numbersf/SCHED_PATCH)

### Community Support

 - **Telegram Channel**: [@qdykernel](https://t.me/qdykernel)
 - **CoolAPK Profile**: [@showdo](http://www.coolapk.com/u/1624571)
 - **GitHub Issues**: [Submit Issue](https://github.com/showdo/Build_Oneplus_Realme_Action/issues)

### Credits

 This project build support from:
 - [HanKuCha](https://github.com/HanKuCha/oneplus13_a5p_sukisu)
 - [cctv18](https://github.com/cctv18) - Toolchain and patch support

---

## 📜 License

This project is licensed under **GPL-3.0**.

```
Copyright (C) 2024 showdo

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
```

---

## 📈 Project Statistics

[![Star History Chart](https://api.star-history.com/svg?repos=showdo/Build_Oneplus_Realme_Action&type=Date)](https://star-history.com/#showdo/Build_Oneplus_Realme_Action&Date)

---

## 📞 Contact

For questions or suggestions, please contact via:

- **Telegram**: [@qdykernel](https://t.me/qdykernel)
- **GitHub Issues**: [Create Issue](https://github.com/showdo/Build_Oneplus_Realme_Action/issues)
- **CoolAPK**: DM [@showdo](http://www.coolapk.com/u/1624571)

---

**Last Updated**: March 15, 2026  
**Maintenance Status**: 🟢 Actively Maintained
