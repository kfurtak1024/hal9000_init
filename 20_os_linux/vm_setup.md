```
██╗   ██╗███╗   ███╗        ███████╗███████╗████████╗██╗   ██╗██████╗ 
██║   ██║████╗ ████║        ██╔════╝██╔════╝╚══██╔══╝██║   ██║██╔══██╗
██║   ██║██╔████╔██║        ███████╗█████╗     ██║   ██║   ██║██████╔╝
╚██╗ ██╔╝██║╚██╔╝██║        ╚════██║██╔══╝     ██║   ██║   ██║██╔═══╝ 
 ╚████╔╝ ██║ ╚═╝ ██║███████╗███████║███████╗   ██║   ╚██████╔╝██║     
  ╚═══╝  ╚═╝     ╚═╝╚══════╝╚══════╝╚══════╝   ╚═╝    ╚═════╝ ╚═╝     
```

For virtualization, I use **QEMU** with **virt-manager** as the graphical frontend.

## 💾 Installation

To install and configure the environment:

```
sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils virt-manager
sudo systemctl enable --now libvirtd
sudo usermod -aG libvirt $(whoami)
```

After running the commands above, reboot or log out and log back in for group membership changes to take effect.

### Notes

- **qemu-kvm** — hardware-accelerated virtualization backend
- **libvirt** — provides management layer and daemon for VM control
- **virt-manager** — GUI tool for creating and managing virtual machines
- **bridge-utils** — enables networking between host and guest (for bridged adapters)

## 📁 VM Directory Structure

All virtual machines are stored under the `~/VMs` directory, with each virtualized system organized in its own subfolder.  
Each VM directory contains three main components:

- `iso/` — installation media and drivers
- `snapshots/` — differential QCOW2 images for experiments or system states
- Base `.qcow2` image — the main disk used as the VM’s root filesystem

This structure allows for a clean separation between base images, temporary snapshots, and installation resources, making it easy to rebuild or restore VMs when needed.

### Example Structure

```
VMs
├── win11
│   ├── iso
│   │   ├── utm-guest-tools-0.1.271.iso
│   │   ├── virtio-win-0.1.271.iso
│   │   └── Win11_25H2_English_x64.iso
│   ├── snapshots
│   │   └── win11_snapshot.qcow2
│   └── win11_base.qcow2
└── ...
```

### Notes

- The **base image** (e.g., `win11_base.qcow2`) remains read-only — it serves as a “golden” system state.
- Active sessions or experiments are done on **snapshot images** stored under `snapshots/`.
- The `iso/` directory holds installation media, drivers (e.g., VirtIO), and guest tools.

