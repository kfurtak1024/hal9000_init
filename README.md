```
██╗  ██╗ █████╗ ██╗     █████╗  ██████╗  ██████╗  ██████╗         ██╗███╗   ██╗██╗████████╗
██║  ██║██╔══██╗██║    ██╔══██╗██╔═████╗██╔═████╗██╔═████╗        ██║████╗  ██║██║╚══██╔══╝
███████║███████║██║    ╚██████║██║██╔██║██║██╔██║██║██╔██║        ██║██╔██╗ ██║██║   ██║   
██╔══██║██╔══██║██║     ╚═══██║████╔╝██║████╔╝██║████╔╝██║        ██║██║╚██╗██║██║   ██║   
██║  ██║██║  ██║███████╗█████╔╝╚██████╔╝╚██████╔╝╚██████╔╝███████╗██║██║ ╚████║██║   ██║   
╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚════╝  ╚═════╝  ╚═════╝  ╚═════╝ ╚══════╝╚═╝╚═╝  ╚═══╝╚═╝   ╚═╝
```
<div align="right"><sup><a href="https://patorjk.com/software/taag/#p=display&f=ANSI+Shadow&t=Type+Something+&x=none&v=4&h=4&w=80&we=false">Banner created using patorjk.com</a></sup></div>

>_"The 9000 series is the most reliable computer ever made."_
> — HAL 9000

## 🧠 HAL9000 Initialization Protocol

<img src="hal9000.svg" alt="HAL 9000" width="180" align="right" style="margin-left: 15px; width: 128px; height:128px">

Welcome to **`hal9000_init`** — a complete technical manual for building, configuring, and restoring my personal workstation.

This repository documents every layer of the system:
from hardware selection, through OS installation and partitioning, to configuration and recovery procedures.

> [!NOTE]
> This is **not a backup**. It’s a _blueprint_ 📐 for reinitializing my system.

## 🎯 Purpose & Usage

The **HAL9000** system serves as my **primary personal and professional machine**, designed for flexibility across multiple high-performance domains:

### 💻 Development
Primarily used for software and game development:
- Software and systems development, including backend and tooling projects.
- **Game development** (Godot, maybe Unreal), requiring high GPU performance and fast compile times.
- Running **Linux** as the main environment for development, with tools like Docker, build chains, and local CI environments.

### 🎮 Gaming
Gaming is primarily done under Windows 11, but I intend to gradually experiment with native Linux gaming (via Steam Proton, Lutris, etc.) to evaluate performance and compatibility.

### 🧠 AI & Experimentation
The system will also be used for local AI experimentation, including testing LLMs, diffusion models, and simulation-based AI tools, with GPU acceleration enabled under Linux.

### 🌐 Remote Work
Some remote work tasks require Windows 11, specifically due to VPN compatibility.
I plan to mitigate this limitation by running Windows 11 in a virtual machine under Linux whenever possible.

## 🧱 Structure

| Section | Description |
|---------|-------------|
| [00_hardware](00_hardware/components.md) | Components list, rationale, and assembly notes |
| [10_setup](10_setup/thermal_setup.md) | Cooling and thermal setup — fan configuration, airflow design, BIOS fan curves, and noise optimization |
| [20_os_linux](20_os_linux/installation.md) | Guides for installing and configuring Pop!_OS, including partitioning, terminal customization, and development environment setup (Docker, Python). Also includes instructions for gaming on Linux, AI setup, and virtualization with QEMU/KVM.<br><ul><li>[AI Setup](20_os_linux/ai.md)</li><li>[Development Setup](20_os_linux/develop.md)</li><li>[Gaming Setup](20_os_linux/gaming.md)</li><li>[Installation](20_os_linux/installation.md)</li><li>[Shell Setup](20_os_linux/shell.md)</li><li>[VM Setup](20_os_linux/vm_setup.md)</li></ul> |
| [30_os_win11](30_os_win11/installation.md) | Installation guide for Windows 11, partitioning details, configuration for VPN compatibility and gaming |

## 📜 License

Personal documentation. 

Feel free to browse and adapt ideas, but this repo is tailored to my specific setup.
