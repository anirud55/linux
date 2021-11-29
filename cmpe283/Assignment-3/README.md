# Aniruddha Narkhede and Surbhi Dogra
# Aniruddha's Contribution
•	Modified the vmx.c file and cupid.c file for the CPUID leaf node %eax=0x4FFFFFFE
•	Tested the changes made in leaf function using cpuid package in the nested VM.
# Surbhi's Contribution
•	Modified the vmx.c file and cupid.c file for the CPUID leaf node %eax=0x4FFFFFFC
•	Tested the changes made in leaf function using cpuid package in the nested VM.

# Steps to reproduce
•	Edited measurement code in vmx.c and reporting code (writes to eax) in cpuid.c.
•	ran make -j 8 modules
•	ran sudo bash
•	ran ‘make INSTALL_MOD_STRIP=1 modules_install && make install’
•	ran ‘lsmod | grep kvm’
•	ran ‘rmmod kvm’
•	ran ‘rmmod kvm_intel’
•	ran ‘modprobe kvm’
•	ran ‘modprobe kvm_intel’
•	In the nested VM run the commands “cpuid -l 0x4ffffffc -s <exit reason>“ and “cpuid -l 0x4ffffffe -s <exit reason>“ to find the number of exits.
•	Please find the screenshots in the screenshots directory.


# Answer to Questions:
•	We notice that there is an increase in the total number of exits as we re-run the commands. After a full reboot we notice there is an exponential increase in the number of exits from 9492 to 116060.
•	We noticed, exit reasons with 0 was least frequent. The most frequent exits were noticed for exit reason =48


