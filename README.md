Documentation for Assignment 1
------------------------------

**By Surbhi Dogra and Aniruddha Narkhede **

(We both performed the assignment on Aniruddha's machine)

**Surbhi\'s contribution**

I worked with Aniruddha to go over the assignment details and review the
lecture recording about the assignment details. On his machine, I
retrieved the starter .c file and makefile and began to add the four
remaining structs and definitions for the different capability info
regions. In the detect\_vmx\_features function, I added the four
remaining reads of the msrs for each capability, and subsequently added
the calls to report\_capability. I then tried to perform testing by
running make, then sudo insmod on the newly created .ko file.

**Aniruddha's Contribution**

Me along with Surbhi worked together to complete the assignment. I
started by creating an Virtual Machine (Ubuntu 20.0) on VMware
Workstation. I then downloaded the Makefile and the .c file on my VM,
and added structs and definitions looking up in SDM for different
capability region, added remaining msrs for each capability and also
report\_capability. For testing the code, i performed \"make\" command,
to make the module, and inserted the module using insmod (using .ko file
created) in kernel, and tracking the \"dmesg\". Initially there was a
permission error, which we resolved using "sudo dmesg" command. I then
created the git repo for the assignment, and i along with Surbhi started
pushing our code to the repository.

**Steps to reproduce**

1.  Installed VMware workstation16

2.  Downloaded ubuntu iso

3.  Created a VM on VMware workstation and assigned RAM of 6GB and 80GB
    Disk Space,8 cores of processors

4.  Used ubuntu iso image for the VM

5.  Enabled nested virtualisation (Enable "Virtualize Intel VT-x/EPT or
    AMD- V/RVI" checkbox)

6.  Powered on the VM and installed ubuntu OS

7.  Verified if nested virtualisation is installed properly by running
    the command "cat /proc/cpuinfo"

8.  Installed htop, git

9.  Forked the git repo torvalds/linux and cloned it to the ubuntu VM

10. retrieve .c file and makefile from canvas

11. Add capability structs based on info from SDM and make calls to
    rdmsr and report\_capability in the .c file

12. in the directory of the .c file and makefile, call \'make\'

13. call \'sudo insmode ./cmpe283-1.ko

14. call sudo dmesg to see capabilities


