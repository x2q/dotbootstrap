---
layout: post
published: true
title: ! 'Linux: Check Ram/Memory Module/Bank Speed and Type'
permalink: /linux-check-rammemory-modulebank-speed-type/
wordpress_id: 1937
categories:
- Linux
- DMI
- Part
---
This is mostly a note to myself.

<a href="http://www.nongnu.org/dmidecode/">Dmidecode</a> reports information about your system's hardware as described in your system BIOS according to the SMBIOS/DMI standard (see a sample output). This information typically includes system manufacturer, model name, serial number, BIOS version, asset tag as well as a lot of other details of varying level of interest and reliability depending on the manufacturer. This will often include usage status for the CPU sockets, expansion slots (e.g. AGP, PCI, ISA) and memory module slots, and the list of I/O ports (e.g. serial, parallel, USB).
DMI data can be used to enable or disable specific portions of kernel code depending on the specific hardware. Thus, one use of dmidecode is for kernel developers to detect system "signatures" and add them to the kernel source code when needed.
Beware that DMI data have proven to be too unreliable to be blindly trusted. Dmidecode does not scan your hardware, it only reports what the BIOS told it to.


```

cc@ea:~$ sudo dmidecode --type 17
# dmidecode 2.9
SMBIOS 2.6 present.

Handle 0x002B, DMI type 17, 28 bytes
Memory Device
	Array Handle: 0x002A
	Error Information Handle: No Error
	Total Width: 64 bits
	Data Width: 64 bits
	Size: 2048 MB
	Form Factor: SODIMM
	Set: None
	Locator: DIMM 1
	Bank Locator: Bank 0/1
	Type: <out OF SPEC>
	Type Detail: Synchronous
	Speed: 1066 MHz (0.9 ns)
	Manufacturer: 80CE            
	Serial Number: 92AA7DD2        
	Asset Tag: 1016
	Part Number: M471B5673FH0-CF8  

Handle 0x002C, DMI type 17, 28 bytes
Memory Device
	Array Handle: 0x002A
	Error Information Handle: No Error
	Total Width: Unknown
	Data Width: Unknown
	Size: No Module Installed
	Form Factor: SODIMM
	Set: None
	Locator: DIMM 2
	Bank Locator: Bank 2/3
	Type: Unknown
	Type Detail: Synchronous
	Speed: Unknown
	Manufacturer:                 
	Serial Number:                 
	Asset Tag:     
	Part Number:                   
</out>
```
