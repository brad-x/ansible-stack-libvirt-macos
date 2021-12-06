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
    -  The stack will use a templated libvirt domain XML to configure networking in lieu of direct libvirt support for QEMU's networking requirements on macOS
- QEMU with vmnet-framework-v5 patches
    - Enabling QEMU to create virtual interfaces on macOS using vmnet framework.
