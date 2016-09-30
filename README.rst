fedora-live-Image
=================

Create fedora live images using livemedia-creator

Prerequisites
-------------

- Fedora system (I tested it with fedora-24)
- lorax package should be installed ( # dnf install lorax) [Tested with lorax-24.20-1.fc24.x86_64]
- libvirt-daemon should be installed

:: 
    
    # rpm -qa | grep libvirt
    libvirt-daemon-driver-qemu-1.3.3.2-1.fc24.x86_64
    libvirt-daemon-driver-nwfilter-1.3.3.2-1.fc24.x86_64
    libvirt-daemon-1.3.3.2-1.fc24.x86_64
    libvirt-daemon-driver-nodedev-1.3.3.2-1.fc24.x86_64
    libvirt-daemon-kvm-1.3.3.2-1.fc24.x86_64
    libvirt-daemon-config-network-1.3.3.2-1.fc24.x86_64
    libvirt-client-1.3.3.2-1.fc24.x86_64
    libvirt-daemon-driver-interface-1.3.3.2-1.fc24.x86_64
    libvirt-daemon-driver-storage-1.3.3.2-1.fc24.x86_64
    libvirt-python3-1.3.3-3.fc24.x86_64
    libvirt-daemon-driver-secret-1.3.3.2-1.fc24.x86_64
    libvirt-python-1.3.3-3.fc24.x86_64
    libvirt-daemon-driver-network-1.3.3.2-1.fc24.x86_64

- libvirtd service should be running ( # systemctl status libvirtd )


Steps
-----

- Download Fedora netinst iso from https://download.fedoraproject.org/pub/fedora/linux/releases/24/Workstation/x86_64/iso/Fedora-Workstation-netinst-x86_64-24-1.2.iso
- Put downloaded fedora netinst iso to same git repo.
- Execute: livemedia-creator --make-iso --iso=/root/livemedia-creator/Fedora-Workstation-netinst-x86_64-24-1.2.iso --ks=/root/livemedia-creator/fedora-minimized.ks
- Once this command complete it will provide you result location like *Results are in /var/tmp/lmc-work-2t9jvryu*
- bootable iso will be in *images* directory and named as *boot.iso*
