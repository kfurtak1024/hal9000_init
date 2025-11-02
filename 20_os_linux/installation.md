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

```
timedatectl set-local-rtc 1 --adjust-system-clock
```

## ✨ Font Rendering Quality

To improve font sharpness and readability on high-resolution displays, install **GNOME Tweaks**:

```
sudo apt install gnome-tweaks
```

Then open GNOME Tweaks and adjust the following settings:

- **Fonts** → **Hinting**: `Full`
- **Fonts** → **Antialiasing**: `Subpixel (RGB)`
- **Fonts** → **Scaling Factor**: `1.25`

These settings provide smoother edges, better contrast, and optimal scaling for 1440p or 4K monitors.

