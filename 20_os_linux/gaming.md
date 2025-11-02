```
 ██████╗  █████╗ ███╗   ███╗██╗███╗   ██╗ ██████╗ 
██╔════╝ ██╔══██╗████╗ ████║██║████╗  ██║██╔════╝ 
██║  ███╗███████║██╔████╔██║██║██╔██╗ ██║██║  ███╗
██║   ██║██╔══██║██║╚██╔╝██║██║██║╚██╗██║██║   ██║
╚██████╔╝██║  ██║██║ ╚═╝ ██║██║██║ ╚████║╚██████╔╝
 ╚═════╝ ╚═╝  ╚═╝╚═╝     ╚═╝╚═╝╚═╝  ╚═══╝ ╚═════╝ 
```

TBD...
## 🎮 Xbox One Controller Driver Installation

To enable support for Xbox One (and Xbox Series) gamepads on Linux, the recommended open-source driver is **xone** — a modern kernel driver and daemon that provides plug-and-play support over USB and wireless adapters.

Repository (forked xone): [https://github.com/dlundqvist/xone](https://github.com/dlundqvist/xone)

### Installation

Install dependencies:

```bash
sudo apt install cabextract
```

Clone the repository and install the driver:

```bash
git clone https://github.com/dlundqvist/xone.git
cd xone
sudo make install
```

The installer automatically builds and loads the kernel module, extracts required firmware, and sets up udev rules.
