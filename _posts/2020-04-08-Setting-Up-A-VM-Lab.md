---
layout: post
title:  "Setting Up a VM Lab for Learning"
date:   2020-04-08 20:00:00 -0900
categories: jekyll update
---

Where to start with lerning penetration testing and vulnerability assessment?  
Easy way is to get your hands dirty and see what is out there. This should give you a great overveiw of what there is to learn and what exactly you want to dive depper in.  
There are many ways how to set up a lab to use with vulnerable images/VM's, but this is what I like to use as it does not expose the outside netowrk which the host machine is connected to, but also allowing the vm's to access the internet
This is particularly useful when using tools like metasploit.  
The gist of the method is to create a network virtually with a router and having all the VMs attached to it, where the router provides an internet connection to the VMs as well as internal networking. The router also does not see any of the host machine netowrk, which provides protection to other machines/appliances which are not supposed to be "learned" on.

Recommended host machine specs (from what experience I have): 

  - Any processor with more than 2 cores made in the last 10 years
  - 8GB+ RAM
  - 120GB+ SSD for VMs *more would be nice, especially when using snapshots
  - Internet connection?

List of things to download:
  - [Virtual box](https://www.virtualbox.org/wiki/Downloads) (my prefered type 2 hypervisor)
  - [pfsense](https://www.pfsense.org/download/) (for your routing needs)
  - [kali linux](https://www.offensive-security.com/kali-linux-vm-vmware-virtualbox-image-download/) (or preferred attacking operating system)
  - target/vulnerable images (I source mine from [vulnhub](https://www.vulnhub.com/) or connect to [hackthebox](https://www.hackthebox.eu/))

Notes for the downloads:
  * for pfsense: make sure you download a AMD64 and ISO image of pfsense
  * kali: get a virtualbox image (64-bit) for convenience

Installation & Configuration:

1. Install virtualbox 
2. Import the kali ova into virtualbox
3. Start the kali image and make sure it works (login changed recently to kali/kali instead of root/toor)
4. Create a new Virtual Machine for pfsense
    a. Name: pfsense
    b. Type: BSD
    c. Version: FreeBSD (64-bit)
    d. RAM: 512MB (or more if you have the luxury)
    e. Create a virtual hard disk --> ~6GB --> VDI --> Dynamically allocated 
  
  
  ---WIP---
