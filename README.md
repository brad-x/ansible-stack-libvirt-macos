QEMU Virtual Networking
===

Architecture Components
---
- vde2 with try/catch patch
    - virtualsquare/vde-2 is used to provide a virtual switch for virtual machines to connect to
- vde_vmnet from Lima project
    - Creates a network interface using the Apple vmnet framework, connecting the vde switch to the host OS
- libvirt
    - Libvirt from MacPorts with the QEMU driver enabled manages virtual machines and their state

TODO: Support vmnet-macos networking in QEMU

Example: -netdev vmnet-macos,id=net0,mode=bridged -device virtio-net-pci,netdev=net0