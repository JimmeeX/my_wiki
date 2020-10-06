# Monitoring

Here are some useful shell commands to monitor or get information about CPU, GPU, Memory, Network, Storage, etc.

## CPU

* [lscpu](https://linux.die.net/man/1/lscpu) - Display information about CPU architecture
* /proc/stat - CPU Usage for each CPU
* ps - CPU Usage by processes
* htop - Similar to ps
* top - Similar to ps

## GPU

Assuming the use of an nvidia driver

* [nvidia-smi](https://developer.nvidia.com/nvidia-system-management-interface) - Information about GPU Driver including gpu and memory utilisation and processes
* [glxinfo](https://dri.freedesktop.org/wiki/glxinfo/) - Diagnose 3D acceleration setup

## Memory

* [free](https://linuxize.com/post/free-command-in-linux/) - Monitor system's memory and SWAP usage.
* ps - Mem usage by processes

## Storage

* \[df\]\([https://en.wikipedia.org/wiki/Df\_\(Unix](https://en.wikipedia.org/wiki/Df_%28Unix)\)\) - Display available disk space

## Network

* ifconfig - IP address for each network interface
* ip addr - Similar to ifconfig
* [nethogs](https://github.com/raboof/nethogs) - Monitor rx/tx of each process
* [/sys/class/net/](https://www.kernel.org/doc/Documentation/ABI/testing/sysfs-class-net) - Gather info about each interface \(eg, total rx/tx\)

I have made use of these commands in my custom AwesomeWM widgets [here](https://github.com/JimmeeX/dotfiles/tree/master/.config/awesome/my-widgets).

