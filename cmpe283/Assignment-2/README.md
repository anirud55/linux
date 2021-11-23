Aniruddha Narkhede and Surbhi Dogra
Aniruddha's Contribution
I added a leaf function under kvm_emulate_cpuid for calculating the total number of exits and storing it in eax register and also spent time reading about atomic variables while doing so. After this, when I was trying to build the kernel for the nested Virtual Machine by running make modules, I faced multiple errors and then ended up wiping our original VM and redoing the steps of Assignment 1 followed by rewriting leaf function in cpuid for total number of exits. I then installed VMware workstation and tried installing debian linux on it to test my code. This gave me some issues due to limited disk space and then uninstalled debian followed by VMware workstation. I then tried installing Virtual Box for the nested VM and then installed ubuntu. While trying to populate number of exits and storing the value in register, we faced the following error : 
ERROR! (dkms apport) : Binary package for virtual box:6.1.26 not found.
ERROR bad return status for module build on kernel : 5.15.0+ (x86_64).
For the third time, I worked with Surbhi to re-install the host VM on VMware workstation followed by Assignment-1 steps. Then, we built the kernel for nested virtualization. Once that was successful, I then installed Virtual Machine Manager, built a nested VM with 4 cores of CPU, 4GB of memory and 20GB of disk space with ubuntu 20.04 OS on it. This was followed by creating a test .c file for printing register values in nested VM and successfully running it.
Surbhi's Contribution
I worked with Aniruddha to add exit measurement code in vmx.c , and reporting information in the cpuid.c leaf function, along with setting up the nested VM, building the linux kernel which failed multiple times. After the final setup, in the same environment, I updated the kvm_emulate_cpuid and added a leaf function for calculating the total number of exits occurred in register ecx due to the value 0x4ffffffd and storing the value in eax. In parallel I spent some time building the kernel for the nested VM. I then created a test file in c for testing the code and then running it.

Steps to reproduce
1.	Edited measurement code in vmx.c and reporting code (writes to eax) in cpuid.c.
2.	ran make -j 8 modules
3.	ran sudo bash
4.	ran ‘make INSTALL_MOD_STRIP=1 modules_install && make install’
5.	ran ‘lsmod | grep kvm’
6.	ran ‘rmmod kvm’
7.	ran ‘rmmod kvm_intel’
8.	ran ‘modprobe kvm’
9.	ran ‘modprobe kvm_intel’
10.	Installed VMM and created a nested ubuntu VM. 
11.	Created testing code that calls cpu in inline assembly.
12.	Observed and printed output