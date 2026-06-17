# Lenovo BatterySetting / 联想电源管理风扇工具

> 从联想电脑管家提取的电源管理与风扇控制独立工具  
> Standalone power management and fan control tool extracted from Lenovo PC Manager

---

## 📋 项目简介 | Overview

本项目是从 **联想电脑管家 (Lenovo PC Manager)** 中提取的电源管理与风扇控制模块，包含以下组件：

| 组件 | 说明 | 版本 |
|------|------|------|
| `BatterySetting.exe` | 联想电源管理主程序 | v5.1.80.8221 |
| `WrapPlugin.dll` | 插件包装层 | v5.1.190.4231 |
| `libcurl.dll` | libcurl 网络库依赖（运行时必需） | — |
| `plugins/IdeaFanPlugin.dll` | 风扇控制插件 | v3.0.600.5201 |
| `skin/lan/zh-cn.dat` | 简体中文字符串资源 | — |

This project is an extracted power management and fan control module from **Lenovo PC Manager**, containing the components above.

### 界面截图 | Screenshot

![Lenovo BatterySetting Interface](docs/images/screenshot.png)

---

## 🔧 功能特性 | Features

- ⚡ **电源管理** - 设置充电阈值（保养模式）、查看电池状态  
  **Battery Management** — Set charge thresholds (conservation mode), view battery status
- 🌬️ **风扇控制** - 调节风扇转速曲线、切换散热模式  
  **Fan Control** — Adjust fan speed curves, switch cooling modes
- 📦 **独立运行** - 无需安装完整联想电脑管家  
  **Standalone** — No need to install the full Lenovo PC Manager package
- 🧩 **插件架构** - 通过 WrapPlugin 加载功能插件  
  **Plugin Architecture** — Load functional plugins via WrapPlugin

---

## 🚀 使用方法 | Usage

### 直接运行 | Run Directly

双击 `BatterySetting.exe` 即可启动电源管理界面。  
Double-click `BatterySetting.exe` to launch the power management interface.

### 命令行参数 | Command Line Arguments

> TODO: 需要逆向分析以确定可用命令行参数  
> TODO: Need reverse engineering to determine available CLI arguments

### 文件结构 | File Structure

```
LenovoBatterySetting/
├── app/
│   ├── BatterySetting.exe        # 主程序 Main executable
│   ├── WrapPlugin.dll            # 插件加载器 Plugin loader
│   ├── plugins/
│   │   └── IdeaFanPlugin.dll     # 风扇控制插件 Fan control plugin
│   └── skin/
│       └── lan/
│           └── zh-cn.dat         # 中文语言资源 Chinese language resources
├── docs/
│   └── images/
│       └── screenshot.png        # 界面截图 Screenshot
├── libcurl.dll                   # libcurl 网络库运行时依赖
└── README.md
```

---

## 📥 安装说明 | Installation

1. 将整个文件夹复制到任意位置（无需安装）
2. 进入 `app/` 目录运行 `BatterySetting.exe`

> **注意**: 请确保以管理员权限运行，否则部分功能（如风扇控制）可能受限。

1. Copy the entire folder to any location (no installation required)
2. Navigate to the `app/` directory and run `BatterySetting.exe`

> **Note**: Run as Administrator for full functionality (fan control may be restricted otherwise).

---

## ⚠️ 注意事项 | Caveats

- 🖥️ **仅适用于联想设备** — 该工具依赖 Lenovo ACPI / 硬件接口  
  **Lenovo devices only** — Depends on Lenovo ACPI / hardware interface
- 🪟 **仅支持 Windows** — 无跨平台支持  
  **Windows only** — No cross-platform support
- 🔒 **需管理员权限** — 风扇控制需要系统级访问  
  **Admin rights required** — Fan control needs system-level access
- 🧪 **仅供研究** — 本项目仅供学习研究使用  
  **For research purposes only** — This project is for educational use

---

## 🔍 技术细节 | Technical Details

- **BatterySetting.exe**: 基于 MFC 的 Windows GUI 应用程序，通过联想 ACPI WMI 接口与硬件通信  
  MFC-based Windows GUI app, communicates with hardware via Lenovo ACPI WMI interface
- **WrapPlugin.dll**: 插件管理框架，负责任何插件的加载/卸载/生命周期管理  
  Plugin management framework for loading/unloading/lifecycle management of plugins
- **IdeaFanPlugin.dll**: 核心风扇控制逻辑，提供转速调节、温度监控等功能  
  Core fan control logic providing speed adjustment, temperature monitoring, etc.

---

## 📄 许可证 | License

本项目仅供学习研究目的。原始软件版权归 **联想集团 (Lenovo Corporation)** 所有。  
This project is for educational and research purposes only. Original software copyright © **Lenovo Corporation**. All rights reserved.

---

## 🙏 致谢 | Acknowledgments

- [联想电脑管家](https://pcmgr.lenovo.com.cn/) — 原始软件来源 Original software source

---

*README 生成于 | Generated: 2026-07*
