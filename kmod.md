# kmod

Multi-call executable that implements: `lsmod`, `insmod`, `rmmod`, and other tools on desktop distros such as Ubuntu 16.04, where e.g.:

    ls -l /bin/lsmod

gives:

    lrwxrwxrwx 1 root root 4 Jul 25 15:35 /bin/lsmod -> kmod

and:

    dpkg -l | grep -Ei

contains:

    ii  kmod                                        22-1ubuntu5                                         amd64        tools for managing Linux kernel modules

BusyBox also implements its own version of those executables. There are some differences.

Buildroot also has a kmod package, but we are not using it since BusyBox' version is good enough so far.

This page will only describe features that differ from kmod to the BusyBox implementation.

Source code: <https://git.kernel.org/pub/scm/utils/kernel/kmod/kmod.git>

## module-init-tools

Name of a predecessor set of tools.

## modprobe

Load module under different name to avoid conflicts:

    sudo modprobe vmhgfs -o vm_hgfs
