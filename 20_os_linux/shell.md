```
███████╗██╗  ██╗███████╗██╗     ██╗     
██╔════╝██║  ██║██╔════╝██║     ██║     
███████╗███████║█████╗  ██║     ██║     
╚════██║██╔══██║██╔══╝  ██║     ██║     
███████║██║  ██║███████╗███████╗███████╗
╚══════╝╚═╝  ╚═╝╚══════╝╚══════╝╚══════╝
```

## 🖋️ Kitty Terminal Installation

[Kitty](https://sw.kovidgoyal.net/kitty/) is a GPU-based terminal emulator with advanced features and high performance.

### 1. Install Kitty

Run the official installer script:

```
curl -L https://sw.kovidgoyal.net/kitty/installer.sh | sh /dev/stdin
```

By default, this installs Kitty to:

```
~/.local/kitty.app/
```

### 2. Make Kitty available as a command

Create a symlink so kitty can be run from anywhere:

```
sudo ln -s ~/.local/kitty.app/bin/kitty /usr/local/bin/
```

### 3. Add Kitty to Desktop Launcher

Copy the desktop entry:

```
cp ~/.local/kitty.app/share/applications/kitty.desktop ~/.local/share/applications/
```

Update paths to Kitty executable and icon in the desktop file:

```
sed -i "s|Icon=kitty|Icon=$(readlink -f ~)/.local/kitty.app/share/icons/hicolor/256x256/apps/kitty.png|g" ~/.local/share/applications/kitty*.desktop
sed -i "s|Exec=kitty|Exec=$(readlink -f ~)/.local/kitty.app/bin/kitty|g" ~/.local/share/applications/kitty*.desktop
```

> [!Note]
> To uninstall Kitty:
> ```
> rm -rf ~/.local/kitty.app
> sudo rm -f /usr/local/bin/kitty
> rm -f ~/.local/share/applications/kitty.desktop
> rm -rf ~/.config/kitty
> ```

> [!Tip]
> Set theme to `Glacier`:
> ```
> kitty +kitten themes
> ```

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

### 7. Install fastfetch

Install fastfetch using the official PPA:
```
sudo add-apt-repository ppa:zhangsongcui3371/fastfetch
sudo apt update
sudo apt install fastfetch
```

Extract **fastfetch** [configuration](.config/config-fastfetch.tar.gz) in home directory.

> [!Note]
> To build configuration from scratch:
> Download the [HAL-9000-500x500.png](https://design-kink.com/wp-content/uploads/2013/04/HAL-9000-1080-500x500.png) and save it as:
> ```
> ~/.config/fastfetch/hal9000.png
> ```
>
> Create the configuration file at `~/.config/fastfetch/config.jsonc`:
> ```
> {
>   "$schema": "https://github.com/fastfetch-cli/fastfetch/raw/master/doc/json_schema.json",
>   "logo": {
>     "type": "kitty-direct",
>     "source": "~/.config/fastfetch/hal9000.png",
>     "width": 26,
>     "padding": {
>       "top": 2,
>       "left": 3,
>       "right": 3
>     }
>   },
>   "modules": [
>     "break",
>     "title",
>     "separator",
>     "os",
>     "kernel",
>     "uptime",
>     "display",
>     "cpu",
>     "gpu",
>     "memory",
>     "swap",
>     "disk",
>     "localip",
>     "break",
>     "colors"
>   ]
> }
> ```
>
> Then, add the following line **at the beginning** of `~/.zshrc file`:
> ```
> if [[ -o interactive ]]; then
>   fastfetch
> fi
> ```

> [!Tip]
> To display **fastfetch** only once after logging in, create a temporary marker by adding following line to '.profile':
> 
> ```
> touch $HOME/.run_only_once
> ```
> 
> Then update `~/.zshrc` to invoke **fastfetch** only if the file exists and the shell is interactive:
> ```
> if [[ -f $HOME/.run_only_once && -o interactive ]]; then
>   rm -f $HOME/.run_only_once
>   fastfetch
> fi
> ```

### 8. Install `bat` (a modern replacement for `cat`)
```
sudo apt install bat
```

### 9. Install `lsd` 🌈 (a modern `ls`)
Download the latest release from [lsd releases](https://github.com/lsd-rs/lsd/releases/) and install it:
```
sudo dpkg -i lsd*.deb
sudo apt -f install
```

### 9. Reinitialize Zsh:
```
source ~/.zshrc
```
