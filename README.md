# linux
Linux kernel source tree

Steps to reproduce

Installed VMware workstation16

Downloaded ubuntu iso

Created a VM on VMware workstation and assigned RAM of 6GB and 80GB Disk Space,8 cores of processors

Used ubuntu iso image for the VM

Enabled nested virtualisation (Enable "Virtualize Intel VT-x/EPT or AMD- V/RVI" checkbox)

Powered on the VM and installed ubuntu OS

Verified if nested virtualisation is installed properly by running the command "cat /proc/cpuinfo"

Installed htop, git

Forked the git repo torvalds/linux and cloned it to the ubuntu VM

retrieve .c file and makefile from canvas

Add capability structs based on info from SDM and make calls to rdmsr and report_capability in the .c file

in the directory of the .c file and makefile, call 'make'

call 'sudo insmode ./cmpe283-1.ko

call sudo dmesg to see capabilities
