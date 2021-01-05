---
title: "Setting up a Active Directory Pentesting Lab"
author: ["Aniket Chauhan"]
date: "2020-12-24"
subject: "Markdown"
keywords: [ActiveDirectory, LabSetup]
subtitle: "AD Lab Setup for Pentesting"
lang: "en"
titlepage: true
titlepage-color: "DC143C"
titlepage-text-color: "FFFAFA"
titlepage-rule-color: "FFFAFA"
titlepage-rule-height: 2
book: true
classoption: oneside
code-block-font-size: \scriptsize 
---

# Task to Accomplish 


1. 		 Work in groups of 3 or individually.
2.       Use VMware, vSphere Hypervisor, and other products from that manufacturer as needed.
3.       Build a system from at least 7 computers with at least 3 real (then at least 4 virtuals). 
4.       Use at least 3 different operating systems.
5.       Create users with different access rights in vSphere Hypervisor.
6.       All computers must be interconnected.
7.       Use more than just the ping command to demonstrate a connection.
8.       Create optional (at least one):
8.1.    Data storage.
8.2.    Web hosting.
8.3.    e-mail.
9.      Capture the workflow (e.g. in screenshots) and provide brief comments.
10.     Give reasons why you have allocated resources (CPU, memory, etc.) in this way.
11.     Clearly separate the work of each group member. If this is not possible, mark such work episodes separately.
12.     Present the results of the work (drawings, diagrams, text documents, presentations, tables) in a way that shows that the system is working (or why it is not working).


# Setting Up the Required Softwares

So for setting up a lab we would need a software to handle virtualization in our case we will be using VMWare's Workstation Pro which can be found here https://www.vmware.com/products/workstation-pro.html . Scrolling down on this page we will find the system requirments and the Operating systems it can be run on. Then there is a download now button which if you press you will transfered over to https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html and here then you can select the OS you want to download the VMWare Workstation Pro for by clicking these buttons.

![](vmware.png)

Clicking this would download the setup file for us opening that up first lets press next and then accept the user agreement by checking the checkbox and pressing next a few times we will have the VMWare Worstation Pro Installed for us now lets move forward to downloading the neccesary ISO files .

So here to setup lets first define the infrastructure of this lab we are gonna make this lab with around 6 computers and machines the OS i have choosen are :

1. Windows 10 x 3 machines 
2. Windows Server 2019
3. Kali Linux 2020.4 
4. Ubunutu 

So now lets start with downloading the Windows 10 and Windows Server 2019 files which we can find here. 

Windows 10 Enterprise : https://www.microsoft.com/en-us/evalcenter/evaluate-windows-10-enterprise
Windows Server 2019 :  https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2019

And here select the ISO file and download them.

![](iso.png)

Then for Kali Linux which our penteration testing Operating System of choice you can also choose Parot OS if you prefer that but here on the link we can find the file download link for the Kali Linux 2020.4 machine.

https://www.offensive-security.com/kali-linux-vm-vmware-virtualbox-image-download/

Download the 64-bit Vmware version and it will need you to have a torrent downloader like utorrent or bittorent. 


Now for Ubuntu we can find the Ubunutu Desktoip 20.04.1 LTS version here. 

Link : https://ubuntu.com/download/desktop

and click the download button for it to download the iso file for us.


# Installing all the Virtual Machines

Now with all the virtual machines ISO files and VMWare files download lets move forward and install them on VMWare so we can use them for setting up our lab.

## Installing our Penetration Testing distribution : Kali Linux

So now that we have our Kali Linux downloaded for vmware. Lets go to the location there will be a .zip file so lets extract it at first to the same folder and then we will have the folder to work with the easiest way to install this is by clicking on the .vmx file and it will open up for us and be all setup 


![](kalivm.png)


So once this is done we can now configure its resouce allocation and settings in the menu

![](kalisettings.png)

These are my current settings and you can ofcourse tweak them around according to your PC specifications and your requirements. and then we can start our kali machine by clicking the first option and then to login we can use the credentials kali:kali and we will be in there.

## Installing Ubuntu 

Now lets go to the File Menu and click on New Virtual Machine and then we will get our Machine Installation wizard and select the typical (recommended option) and press next.

![](ubuntuwizard.png)

And now we have to select the ISO file here in the Installer Disk Image file section which we downloaded for Ubuntu. 

![](ubuntuiso.png)

Then we can choose the username and password of our machine like below 

![](userubuntu.png)

and then pressing next we can rename our server and so on and then we can choose a Maximum disk size for me i chose this to be 20GB and depending on your use case you can choose the option to either all the storage as one file or we can split the disk into multiple files, i choose the later option and then press finish.

Then we can start the virtual machine and it will check the disks at first which can take a little bit of time and then we will then be logged in and it will check the installed file and pop up the Welcome to Ubuntu wizard which is gonna install packages and copy some files for us which can again take some time and then we can login after all this is done using the credentials we set at first.

![](ubuntuinstall.png)

Then we can try downloading our tools in my case i downloaded net-tools so that i can use commands like ifconfig etc. and doing a simple Ifconfig we can see that the server is working and its IPaddress now to check connectivity what i wanted to do was ping this IP from our Kali Linux Machine

![](ifconfig.png)

and then we can see the results of pinging the server here :

![](kaliping.png)

## Installing Windows Server 

So after we have our Windows Server and VMWare Workstation installed lets go to VMWare Workstation and then click the button create a new virtual machine 

![](createvm.png)

Now after clicking on it we will get a pop up for the wizard and we should just click next with the Typical(Recommended) option selected.

![](install1.png)