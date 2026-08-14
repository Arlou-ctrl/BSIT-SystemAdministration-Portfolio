Week 03 – Ubuntu Server Deployment
Project Overview

This project focuses on deploying and configuring an Ubuntu Server virtual machine using recommended system administration practices. The activity was completed in a virtual environment and included the installation of Ubuntu Server, basic server configuration, SSH setup, system verification, and troubleshooting.

The main purpose of this project was to gain practical experience in preparing a Linux server that could later be used for services such as file sharing, web hosting, database hosting, and remote administration. The project also included learning about BIOS and UEFI, understanding the Ubuntu boot process, and documenting the installation so that another administrator could reproduce the setup.

Learning Objectives

After completing this project, I was able to:

Understand the role of an operating system in an enterprise environment.
Install Ubuntu Server in a virtual machine.
Configure basic server settings such as hostname, user account, storage, and networking.
Enable and verify the OpenSSH Server service.
Verify server connectivity and system functionality using Linux commands.
Understand the differences between BIOS and UEFI.
Understand the basic boot process of an Ubuntu Server.
Troubleshoot common virtualization and installation problems.
Document the server deployment process professionally.
Virtual Machine Specifications
Component	Configuration
Virtual Machine Name	Ubuntu-Server-Week03
Operating System	Ubuntu Server LTS
RAM	4 GB
CPU	2 Virtual Processors
Storage	40 GB
Disk Type	VDI
Network	NAT
Installation Media	Ubuntu Server LTS ISO
Hostname	server01
SSH	OpenSSH Server
Installation Summary

Ubuntu Server LTS was installed using a virtual machine. Before starting the installation, I configured the required RAM, CPU, storage, network adapter, and Ubuntu Server ISO.

During the installation, I selected English as the language and used the appropriate keyboard layout. The network was configured using DHCP, allowing the server to automatically receive an IP address. The hostname was set to server01, and a non-root administrative user was created.

For disk configuration, I used the guided option to use the entire virtual disk. OpenSSH Server was also selected during installation to allow secure remote administration.

After the installation was completed, the virtual machine was restarted and the Ubuntu Server system was accessed using the created user account.

Configuration Summary

The following basic configurations were completed:

Hostname configured as server01
Non-root administrative user created
Network configured using DHCP
NAT network adapter enabled
40 GB virtual disk configured
OpenSSH Server installed
System packages updated
Server connectivity tested
SSH service verified

The server was also updated using:

sudo apt update
sudo apt upgrade -y

Verification Results

After completing the installation, several commands were used to verify that the server was working correctly.

Hostname Verification

Command:

hostname


Expected result:

server01


The command confirmed that the hostname was correctly configured.

IP Address Verification

Command:

ip addr


The command was used to identify the IP address assigned to the server through DHCP.

Internet Connectivity

Command:

ping -c 4 google.com


The server successfully received responses, confirming that the network connection and internet connectivity were working.

System Update

Commands:

sudo apt update
sudo apt upgrade -y


The Ubuntu package lists were updated and available system packages were upgraded successfully.

SSH Verification

Command:

systemctl status ssh


The SSH service was verified and showed that it was active and running.

BIOS vs UEFI Highlights
Feature	BIOS	UEFI
Full Name	Basic Input/Output System	Unified Extensible Firmware Interface
Boot Process	Uses traditional boot process	Uses a more modern boot manager
Partition Style	Commonly uses MBR	Commonly uses GPT
Disk Support	More limited with traditional MBR	Supports very large disks using GPT
Security	Limited security features	Supports features such as Secure Boot
Interface	Usually text-based	Can provide a more modern interface
Speed	Generally slower	Generally faster
Modern Usage	Mostly found on older systems	Standard on most modern computers

UEFI has largely replaced BIOS because it provides better support for modern hardware, larger storage devices, faster booting, and improved security features. One important feature is Secure Boot, which helps prevent unauthorized software from running during the boot process.

Embedded Boot Process Flowchart

The Ubuntu Server boot process can be summarized as:

+----------------+
|    Power On    |
+-------+--------+
        |
        v
+-------------------------+
| BIOS / UEFI             |
| Hardware Initialization |
+-----------+-------------+
            |
            v
+-------------------------+
|   Boot Device Detection |
+-----------+-------------+
            |
            v
+-------------------------+
|      GRUB Boot Loader   |
+-----------+-------------+
            |
            v
+-------------------------+
|      Linux Kernel       |
+-----------+-------------+
            |
            v
+-------------------------+
|      init / systemd     |
+-----------+-------------+
            |
            v
+-------------------------+
|     Services Start      |
+-----------+-------------+
            |
            v
+-------------------------+
|      Login Prompt       |
+-------------------------+


The process begins when the computer is powered on. BIOS or UEFI initializes the hardware and searches for a bootable device. The GRUB boot loader then loads the Linux kernel. After the kernel starts, systemd initializes the remaining parts of the operating system and starts the required services. Finally, the user is presented with the login prompt.

Challenges Encountered

One of the main problems I encountered was that hardware virtualization was disabled on my computer. Because of this, the virtual machine could not run properly. I had to restart the computer, enter the BIOS/UEFI settings, and enable the virtualization feature. After saving the changes and restarting, the virtual machine was able to run normally.

I also encountered an issue with making sure that the Ubuntu Server ISO was properly connected to the virtual machine. I checked the virtual machine's storage settings and attached the ISO to the optical drive.

Another challenge was identifying the IP address assigned through DHCP. I used the ip addr command to check the network interface and find the assigned address.

These problems helped me understand that checking the host computer and virtual machine settings before installation can prevent many issues.

Reflection

This project gave me a better understanding of what is involved in deploying an operating system for an enterprise environment. Before doing the activity, I thought that installing Ubuntu Server would mainly involve following the installation wizard. However, I learned that there are several important things to consider before, during, and after the installation.

One of the most memorable problems I encountered was having hardware virtualization turned off. I initially could not properly run my Ubuntu Server virtual machine because virtualization was disabled. I had to access the BIOS/UEFI settings and enable virtualization before continuing. This experience helped me understand that firmware settings can have a direct effect on virtualization and operating system deployment.

I also became more comfortable using Linux commands for server administration. Commands such as hostname, ip addr, ping, sudo apt update, sudo apt upgrade -y, and systemctl status ssh allowed me to check different parts of the server and confirm that everything was working correctly. I learned that verification is an important part of system administration because a successful installation does not always mean that every service is functioning properly.

Another important lesson was the difference between BIOS and UEFI. I learned that UEFI is the newer firmware technology and provides advantages such as support for GPT, larger storage devices, faster boot processes, and security features like Secure Boot.

Overall, this project improved my confidence in working with Ubuntu Server and virtual machines. It also taught me that troubleshooting, documentation, and verification are just as important as the installation itself. As a future IT professional, I understand that keeping clear documentation can make it much easier for another administrator to maintain or troubleshoot a server.

References

Ubuntu Documentation. Ubuntu Server Documentation.
https://documentation.ubuntu.com/server/

Ubuntu. Ubuntu Server.
https://ubuntu.com/server

Oracle. Oracle VM VirtualBox Documentation.
https://www.virtualbox.org/wiki/Documentation

Unified Extensible Firmware Interface Forum. UEFI Specifications and Resources.
https://uefi.org/

GNU GRUB. GNU GRUB Manual.
https://www.gnu.org/software/grub/manual/