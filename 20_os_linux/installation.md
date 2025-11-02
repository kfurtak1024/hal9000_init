```
 ██████╗ ███████╗        ██╗     ██╗███╗   ██╗██╗   ██╗██╗  ██╗
██╔═══██╗██╔════╝        ██║     ██║████╗  ██║██║   ██║╚██╗██╔╝
██║   ██║███████╗        ██║     ██║██╔██╗ ██║██║   ██║ ╚███╔╝ 
██║   ██║╚════██║        ██║     ██║██║╚██╗██║██║   ██║ ██╔██╗ 
╚██████╔╝███████║███████╗███████╗██║██║ ╚████║╚██████╔╝██╔╝ ██╗
 ╚═════╝ ╚══════╝╚══════╝╚══════╝╚═╝╚═╝  ╚═══╝ ╚═════╝ ╚═╝  ╚═╝
```
>_"I feel much better now. I really do."_
> — HAL 9000

## 🧩 Partitioning the Drive

For my drive, I’m using the default partition layout suggested by Pop!_OS during installation. The main change I’m making is to format the system partition as Btrfs. Within it, I’ve created two subvolumes: one for `/` and one for `/home`.

I’m following this excellent [guide](https://mutschler.dev/linux/pop-os-btrfs-22-04/).

## 🕙 Fix time in Dual Boot setup

Since I’m using Windows 11 and Linux in a dual boot configuration, I need to align how both systems handle the hardware clock.
To do this, let’s configure Linux to use **local time**:

```bash
timedatectl set-local-rtc 1 --adjust-system-clock
```

## ✨ Font Rendering Quality

To improve font sharpness and readability on high-resolution displays, install **GNOME Tweaks**:

```bash
sudo apt install gnome-tweaks
```

Then open GNOME Tweaks and adjust the following settings:

- **Fonts** → **Hinting**: `Full`
- **Fonts** → **Antialiasing**: `Subpixel (RGB)`
- **Fonts** → **Scaling Factor**: `1.25`

These settings provide smoother edges, better contrast, and optimal scaling for 1440p or 4K monitors.

## 🌈 OpenRazer and Polychromatic

> [!IMPORTANT]
> Do not use **Pop!_Shop** for **Polychromatic**. Install both **OpenRazer** and **Polychromatic** using apt.
> ```bash
> apt install openrazer polychromatic
> ```

Download and extract [polychromatic effects](.config/config_polychromatic.tar.gz):
```bash
tar xvf config_polychromatic.tar.gz -C ~
```

> [!IMPORTANT]
> By default, only privileged users can access USB devices directly.
> To allow your regular user account to control Razer devices (required by **OpenRazer** and **Polychromatic**), add user to the plugdev group:
> ```bash
> sudo gpasswd -a $USER plugdev
> ```

## 🖨️ Xerox B235 Setup

To enable network discovery and printing for the **Xerox B235** over Wi-Fi using **mDNS (Multicast DNS)**, follow these steps:

### 1. Enable `mdns4` in `/etc/nsswitch.conf`

Edit the file:
```bash
sudo nano /etc/nsswitch.conf
```

Find the line starting with 'hosts:' and update it from:
```
hosts:          files mdns4_minimal [NOTFOUND=return] dns myhostname mymachines
```

to:
```
hosts:          files mdns4_minimal [NOTFOUND=continue] mdns4 dns myhostname mymachines
```

This ensures proper name resolution for printers and other devices advertised via mDNS (e.g., `printer.local`).

### 2. Allow mDNS lookups in `systemd-resolved`

Edit the configuration file:
```bash
sudo nano /etc/systemd/resolved.conf
```
Uncomment (or add) the `MulticastDNS` line under `[Resolve]` and set it to `yes`:
```
MulticastDNS=yes
```

Then restart the service:
```bash
sudo systemctl restart systemd-resolved
```

### 3. Enable mDNS on your Wi-Fi interface

Enable mDNS for your active network interface (replace `wlp8s0` if differs):
```bash
sudo resolvectl mdns wlp8s0 yes
```

Verify that it’s enabled:
```bash
resolvectl status wlp8s0
```
`+mDNS` should be listed under Protocols for that interface.
