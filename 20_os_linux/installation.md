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

## 🖥️ Terminal configuration

### 1. Install Hack Nerd Font
Download and install the latest version of Hack Nerd Font (for example: [Hack.zip v3.4.0](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.4.0/Hack.zip)).

### 2. Install Zsh
```
sudo apt install zsh
```

### 3. Enhance Zsh with Oh My Zsh
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### 4. Install Powerlevel10k theme
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k
```
Then, change the default theme in `~/.zshrc`:
```
ZSH_THEME="powerlevel10k/powerlevel10k"
```

> [!Note]
> To re-run **Powerlevel10k** configuration wizard run:
>
> ```
> p10k configure
> ```

### 5. Install zsh-autosuggestions
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
Add zsh-autosuggestions to the plugins list in `~/.zshrc`:
```
plugins=(... zsh-autosuggestions)
```

### 6. Install zsh-syntax-highlighting
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
And add it to the plugins list in `~/.zshrc`.

### 7. Install `bat` (a modern replacement for `cat`)
```
sudo apt install bat
```

### 8. Install `lsd` 🌈 (a modern `ls`)
Download the latest release from [lsd releases](https://github.com/lsd-rs/lsd/releases/) and install it:
```
sudo dpkg -i lsd*.deb
sudo apt -f install
```

### 9. Reinitialize Zsh:
```
source ~/.zshr
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
