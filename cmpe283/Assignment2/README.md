#Assignment2

Steps to Reproduce:

Modifying Kernel code:

Modify cpuid.c and vmx.c files accordingly to implement the given functionalities :

  To calculate the total number of exits
  
  To return the low 32bits and high 32 bits of the total time spent
    processing all exits
    
  To calculate the number of exits based on the exit provided as
    input.
    
  To return the low 32bits and high 32 bits of the total time spent
    processing for the exit provided as input.
    
Note: file locations : cpuid.c - linux/arch/x86/kvm/cpuid.c
vmx.c - linux/arch/x86/kvm/vmx/vmx.c

Rebuild the kernel using the following command.

  sudo make -j 2 modules M=arch/x86/kvm ( use command nproc
to know no. of CPUs)

Now, perform loading and unloading of kvm kernel module (kvm.ko)
and kvm-intel-module (kvm-intel.ko) using the following commands:

  sudo rmmod arch/x86/kvm/kvm-intel.ko
  
  sudo rmmod arch/x86/kvm/kvm.ko
  
  sudo insmod arch/x86/kvm/kvm.ko
  
  sudo insmod arch/x86/kvm/kvm-intel.ko
  
  
#Testing 

sudo apt-get update

sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils virt-manager

sudo apt-get update

sudo apt-get install cpuid

Create test codes for all the functionalities in the inner with file name test_assignment2.c

Now install gcc and compile the code using gcc

test_Assignment2.c

Now run the test file with ./a.out
