# linux

Steps to Reproduce:

1. Created a VM instance on GCP using below command

gcloud compute instances create cmpe283-vm --enable-nested-virtualization --zone=us-west1-b --machine-type=n2-standard-8 --network-interface=network-tier=PREMIUM,subnet=default --create-disk=auto-delete=yes,boot=yes,device-name=instance-1,image=projects/ubuntu-os-cloud/global/images/ubuntu-2004-focal-v20220204,mode=rw,size=200,type=projects/sjsu-spring-2022/zones/us-central1-a/diskTypes/pd-ssd --metadata=ssh-keys=mlarkin:"...paste ssh key here..."

Make sure you put your desired username and ssh key in the last part, eg:

--metadata=ssh-keys=mlarkin:"...paste ssh key here..."

2. Verified if nested virtualisation is installed properly by running the command "cat /proc/cpuinfo"

3. Installed htop, git

4. Forked the git repo torvalds/linux and cloned it to the ubuntu VM

5. retrieve .c file and makefile from canvas

6. Add capability structs based on info from SDM and make calls to rdmsr and report_capability in the .c file

in the directory of the .c file and makefile, call 'make'

7. call 'sudo insmode ./cmpe283-1.ko

8. call sudo dmesg to see capabilities
