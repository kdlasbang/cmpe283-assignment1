# cmpe283-assignment1
Discover VMX features 
This assignment is to create a Linux kernel module that will query various MSRs to determine virtualization features available in your CPU. This module will report (via the system message log) the features it discovers.

Team Member: Just myself

Implement step:
	1. Fork the https://github.com/torvalds/linux
	2. Clone repo to local. Terminal-> git clone git@github.com:kdlasbang/linux.git (remember to make connection between VM and github account , setting up some authentication and ssh key)
	3. Create new repo -> assignment1 and copy Makefile and cmpe293-1.c into it. (some linux command may need to install, like make)
	4. Terminal -> "sudo apt-get install libncurses-dev gawk flex bison openssl libssl-dev dkms libelf-dev libudev-dev libpci-dev libiberty-dev autoconf"   (This command used for build the kernal later) 
	5. Start do the assignment (following with the instruction video) We need to check these control capability:   PINBASED , PROCBASED, SECONDARY PROCBASED, EXIT, ENTRY. The PINBASED already completed by the instructor. I just need to filled the others.  And I just need to copy and paste the Function detect_vmx_features and capability_info pinbased, then make some modification on it. For the detect_vmx_features, there is nothing to change, we just need to update MSR index by chaging MSR name. While for capability_info, I need to do some research , and find out the control capability need to check, and their Bit position.
	6. We can find other control capability from Intel manaul Volume 3, Chapter 24.6 VM-EXECUTION CONTROL FIELDS. (https://www.intel.com/content/dam/www/public/us/en/documents/manuals/64-ia-32-architectures-software-developer-vol-3c-part-3-manual.pdf)
	7. Fill them out. And check the outcome. 
	8. make 
	9. sudo insmod ./cmpe283-1.ko
	10. sudo rmmod cmpe283-1.ko
	11.sudo insmod cmpe283-1.ko
	12.dmesg
	Done




   
