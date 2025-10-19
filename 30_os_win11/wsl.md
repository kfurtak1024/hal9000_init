```
██╗    ██╗███████╗██╗     
██║    ██║██╔════╝██║     
██║ █╗ ██║███████╗██║     
██║███╗██║╚════██║██║     
╚███╔███╔╝███████║███████╗
 ╚══╝╚══╝ ╚══════╝╚══════╝
```

## Installation

1. Install WSL:
```
wsl --install
wsl --install -d Ubuntu
```

2. Move installed distro to my second parition:
```
mkdir D:\WSL
wsl --export Ubuntu D:\WSL\ubuntu_backup.tar
wsl --unregister Ubuntu
wsl --import Ubuntu D:\WSL\Ubuntu D:\WSL\ubuntu_backup.tar --version 2
rm D:\WSL\ubuntu_backup.tar
```
