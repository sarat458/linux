# Assignment 3

## Work Distribution

### SARAT KUMAR KANITI
* Created leaf node %eax=0x4FFFFFFE - Case 2
* Modified cpuid.c and vmx.c as per the requirement
* Tested and verified the result
* Documented the steps and results


### SRIKANTH NIMMAGADDA
* Created leaf node %eax=0x4FFFFFFC - Case 4
* Modified cpuid.c and vmx.c as per the requirement
* Tested and verified the result
* Documented the steps and results

### STEPS TO REPRODUCE
Modify vmx.c and cpuid.c as per as the requirement.
* For CPUID leaf node %eax= 0x4FFFFFFE:
  * Return the higher 32 bits of the total time taken to process all exits in %ebx
  * Return the lower 32 bits of the total time taken to process all exits in %ecx
  * The values returned by %ebx and %ecx is measured across all VCPUs in every processor cycle.

* For CPUID leaf node %eax= 0x4FFFFFFC:
* Return the time taken to process the exit number provided (on input) in %ecx.
* Return the higher 32 bits of the total time taken to process all exits in %ebx
* Return the lower 32 bits of the total time taken to process all exits in %ecx
* Run "sudo make modules", "sudo make modules_install", "sudo make install" and reboot
* open virt-manager and start vm.
* Install cpuid inside inner vm using "sudo apt-get install cpuid

## CASE 2

* cpuid -l 0x4FFFFFFE
![Alt text](https://github.com/sarat458/linux/blob/master/cmpe283/Assignment3/Output/ASSIGNMENT%203%20IMAGE%201.png "Optional title")

![Alt text](https://github.com/sarat458/linux/blob/master/cmpe283/Assignment3/Output/ASSIGNMENT%203%20IMAGE%202.png "Optional title")

![Alt text](https://github.com/sarat458/linux/blob/master/cmpe283/Assignment3/Output/ASSIGNMENT%203%20IMAGE3.png "Optional title")

* cpuid -l 0x4FFFFFFC s -32

![Alt text](https://github.com/sarat458/linux/blob/master/cmpe283/Assignment3/Output/ASSIGNMENT%203%20IMAGE%204.png "Optional title")

![Alt text](https://github.com/sarat458/linux/blob/master/cmpe283/Assignment3/Output/ASSIGNMENT%203%20IMAGE%205.png "Optional title")

![Alt text](https://github.com/sarat458/linux/blob/master/cmpe283/Assignment3/Output/ASSIGNMENT%203%20IMAGE%206.png "Optional title")

