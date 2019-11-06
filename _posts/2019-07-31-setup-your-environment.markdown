---
layout: post
title:  "Setup Your Environment"
date:   2019-07-31
categories: 
---

### Resources:
* Hardware: :hammer_and_wrench:
	* CPU: Intel -7-3920XM CPU @ 2.90 GHz
	* RAM: 32 GB 
	* GRAPHICS: NVIDIA Quadro K1000M
* Software: :hash:
	* Windows 10 Pro - 1903
	* [VMware® Workstation 15 Pro][VMWARE]
	* [Hash Checker][HASH]

### Setup Process 
1. Download, Verify Hash & Install [VMWARE Workstation][VMWARE] or [Oracle VirtualBox][ORACLE] 
2. Install Kali
```
VMWARE 
New Virtual Machine Wizard
Select a Guest Operating System
Guest operating system: Linux
Version: Other Linux 4.x or later kernel 64-bit
```
You can verify the Version from [Kali's release page][KALI]. In my example, what is listed is *Kali 2019.2 – 21st May, 2019 – The second 2019 Kali Rolling release. <mark>Kernel 4.19.28</mark>, GNOME 3.30.2.*
3. Configure Virtual Machine Hardware Settings
*	Procesors: In order to determine the **Number of Cores** and **Number of cores per processor** to assign to the virtual machine:
		*	Open Task Manager
			*	Performance
				*	CPU
*	Display: To dermine the **Maximum amount of guest memory that can be used for graphics memory**
		*	Open Task Manager
			*	Performance 
				*	GPU

4. Setup Kali
	*	Create a user with sudo privileges and set their login shell
		*	It is advisable to avoid using **root** and instead to **sudo** in order to avoid making inadvertent or irriversible changes to your system.	
```console
root@kali:~# adduser <username>
root@kali:~# usermod -a -G sudo <username>
```
		* logout from root and log back in as your newly created user
* update Kali packages index list and upgrade all packages
		* This may take awhile so get get some :coffee:
```console
# sudo apt update
# sudo apt upgrade
```

5. Download, Verify Hash & Install [VMWARE Workstation][VMWARE] or [Oracle VirtualBox][ORACLE] 
	* I am doing this in order to constrain vulnerable OSs within Kali    
<br/>
6. Take a Snapshot of your VM incase you need to revert changes
	* Right Click VM name in Library Panel
		* Snapshot
			* Take Snapshot...   
<br/>
7. Head over to [VulnHub][VULNHUB] and grab an image 

[VMWARE]: https://www.vmware.com/products/workstation-pro.html
[HASH]: https://hashchecker.net/
[ORACLE]: https://www.virtualbox.org/
[KALI]: https://www.kali.org/kali-linux-releases/
[VULNHUB]: https://www.vulnhub.com/