```
██╗  ██╗ █████╗ ██╗     █████╗  ██████╗  ██████╗  ██████╗         ██╗███╗   ██╗██╗████████╗
██║  ██║██╔══██╗██║    ██╔══██╗██╔═████╗██╔═████╗██╔═████╗        ██║████╗  ██║██║╚══██╔══╝
███████║███████║██║    ╚██████║██║██╔██║██║██╔██║██║██╔██║        ██║██╔██╗ ██║██║   ██║   
██╔══██║██╔══██║██║     ╚═══██║████╔╝██║████╔╝██║████╔╝██║        ██║██║╚██╗██║██║   ██║   
██║  ██║██║  ██║███████╗█████╔╝╚██████╔╝╚██████╔╝╚██████╔╝███████╗██║██║ ╚████║██║   ██║   
╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚════╝  ╚═════╝  ╚═════╝  ╚═════╝ ╚══════╝╚═╝╚═╝  ╚═══╝╚═╝   ╚═╝
```
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

| Section                                  | Description                                                                                                                                                |
|------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [00_hardware](00_hardware/components.md) | Components list, rationale, and assembly notes                                                                                                             |
| [10_os_linux](10_os_linux/overview.md)   | Step-by-step guide for installing Pop!_OS as the main OS, partitioning the drive, configuring development tools, and optionally running Windows 11 as a VM |
| [20_os_win11](20_os_win11/overview.md)   | Installation guide for Windows 11, partitioning details, configuration for VPN compatibility and gaming                                                    |

## 📜 License

Personal documentation. 
Feel free to browse and adapt ideas, but this repo is tailored to my specific setup.
