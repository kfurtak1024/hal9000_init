```
 ██████╗ ███████╗        ██╗    ██╗██╗███╗   ██╗ ██╗ ██╗
██╔═══██╗██╔════╝        ██║    ██║██║████╗  ██║███║███║
██║   ██║███████╗        ██║ █╗ ██║██║██╔██╗ ██║╚██║╚██║
██║   ██║╚════██║        ██║███╗██║██║██║╚██╗██║ ██║ ██║
╚██████╔╝███████║███████╗╚███╔███╔╝██║██║ ╚████║ ██║ ██║
 ╚═════╝ ╚══════╝╚══════╝ ╚══╝╚══╝ ╚═╝╚═╝  ╚═══╝ ╚═╝ ╚═╝
```
>_"I think you know what the problem is just as well as I do."_
> — HAL 9000

## 💿 Installation

Since the Wi-Fi module on the **MSI MAG X870E TOMAHAWK WIFI** motherboard is not detected by the default **Windows 11 installer**, it’s necessary to either:
- Use a USB drive containing the network drivers, or
- Install Windows 11 in offline mode.

To install offline:

1. When the Windows setup screen appears, open the Command Prompt by pressing <kbd>Shift</kbd> + <kbd>F10</kbd>.
2. Enter the following command and press Enter:
  ```OOBE\BYPASSNRO```

This will restart the setup and allow you to continue the installation without an internet connection.

After completing the installation, use a USB drive with the Wi-Fi and chipset drivers downloaded from the MSI MAG X870E TOMAHAWK WIFI [support page](https://www.msi.com/Motherboard/MAG-X870e-TOMAHAWK-WIFI/support#driver)

## 💾 Additional Software

- [FPS Monitor](https://fpsmon.com/en/) - displays an FPS and performance statistics overlay while gaming
- [Samsung Magician Software](https://semiconductor.samsung.com/consumer-storage/magician/) - used for monitoring and updating the firmware of Samsung SSDs

## 🖥️ Terminal Setup

### Fonts

I’m using the following fonts for the Windows Terminal:
- [CascadiaMono Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.4.0/CascadiaMono.zip) → `CaskaydiaMonoNerdFont-Regular.ttf`
- [UbuntuMono Nerd Font](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.4.0/UbuntuMono.zip) → `UbuntuMonoNerdFont-Regular.ttf`

### Oh My Posh

I use Oh My Posh to enhance the prompt appearance in Windows Terminal.

- Setup for Ubuntu (WSL):
  Install _Oh My Posh_:
  ```
  curl -s https://ohmyposh.dev/install.sh | bash -s
  ```
  Add the following line at the end of `~/.profile`:
  ```
  eval "$(oh-my-posh init bash)"
  ```
- Setup for PowerShell
  Install _Oh My Posh_:
  ```
  winget install JanDeDobbeleer.OhMyPosh --source winget --scope user --force
  ```
  Create the profile:
  ```
  New-Item -Path $PROFILE -Type File -Force
  ```
  Allow running remote scripts (run as Administrator):
  ```
  Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
  ```
  Add the following line at the end profile (located at `$PROFILE`):
  ```
  oh-my-posh init pwsh | Invoke-Expression
  ```
