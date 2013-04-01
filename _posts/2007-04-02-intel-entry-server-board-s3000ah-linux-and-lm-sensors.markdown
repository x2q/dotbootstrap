---
layout: post
published: true
title: ! 'Intel Entry Server Board S3000AH: Linux and lm-sensors'
permalink: /intel-entry-server-board-s3000ah-linux-and-lm-sensors/
wordpress_id: 405
categories:
- Links
- Linux
- Open Standards
- Open Source
- Debian
- Ubuntu
- pdf
- Ethernet
- perl
- driver
- PCI Express Port
- Host bridge
- ISA bridge
- PCI bridge
- LPC Interface Bridge
- Express Root Port
- Some chips
- I2C address 0x52 Chip
- Found unknown chip
- data storage chips
- I2C address 0x50 Chip
- Some Super I/O chips
- Gigabit Ethernet
- SMBus Controller
- IDE Controller
- Use driver
- compatible controller
- USB2 EHCI Controller
- Ethernet controller
- USB Controller
- E7230 Memory Controller
- Serial ATA Storage Controller
- National Semiconductor
- Analog Devices
- ATI Technologies Inc
- Intel Corporation
- Texas Instruments
- 82801GB/GR
- 82801GR/GH
- 82573V Gigabit Ethernet Controller
- unknown chip
- Intel 82801GB ICH7 - SMBus Controller [A-1]
- LM-sensor intel server
- Intel AMB FB-DIMM thermal sensor
---


A while ago I bought a <a href="http://www.intel.com/p/en_US/support">Intel Entry Server Board S3000AH </a>( <a href="">Product Information in PDF</a> )

The board features something <a href="http://en.wikipedia.org/wiki/Intel">Intel</a> calls Active Management Technology, which should be able to monitor hardware temperatures etc. The technical product specification says that the board features a <a href="http://www.smsc.com/">SMSC</a> SCH5027D Super I/O Chip, but lm-sensors are unable to detect the <a href="http://www.smsc.com/">SMSC</a> SCH5027D Super I/O Chip correctly.


```

debian14:~# perl sensors-detect.pl
# sensors-detect revision $Revision$

This program will help you determine which kernel modules you need
to load to use lm_sensors most effectively. It is generally safe
and recommended to accept the default answers to all questions,
unless you know what you're doing.

We can start with probing for (PCI) I2C or SMBus adapters.
Do you want to probe now? (YES/no):
Probing for PCI bus adapters...
Use driver `i2c-i801' for device 0000:00:1f.3: Intel 82801G ICH7

We will now try to load each adapter module in turn.
Module `i2c-i801' already loaded.
If you have undetectable or unsupported adapters, you can have them
scanned by manually loading the modules before running this script.

To continue, we need module `i2c-dev' to be loaded.
Do you want to load `i2c-dev' now? (YES/no):
Module loaded successfully.

We are now going to do the I2C/SMBus adapter probings. Some chips may
be double detected; we choose the one with the highest confidence
value in that case.
If you found that the adapter hung after probing a certain address,
you can specify that address to remain unprobed.

Next adapter: SMBus I801 adapter at 3000 (i2c-0)
Do you want to scan it? (YES/no/selectively):
Client found at address 0x2e
Probing for `Myson MTP008'...                               No
Probing for `National Semiconductor LM78'...                No
Probing for `National Semiconductor LM78-J'...              No
Probing for `National Semiconductor LM79'...                No
Probing for `National Semiconductor LM80'...                No
Probing for `National Semiconductor LM85 or LM96000'...     No
Probing for `Analog Devices ADM1027, ADT7460 or ADT7463'... No
Probing for `SMSC EMC6D100, EMC6D101 or EMC6D102'...        No
Probing for `Analog Devices ADT7462'...                     No
Probing for `Analog Devices ADT7467 or ADT7468'...          No
Probing for `Analog Devices ADT7470'...                     No
Probing for `Analog Devices ADT7473'...                     No
Probing for `Analog Devices ADT7475'...                     No
Probing for `Analog Devices ADT7476'...                     No
Probing for `Andigilog aSC7611'...                          No
Probing for `Andigilog aSC7621'...                          No
Probing for `National Semiconductor LM87'...                No
Probing for `National Semiconductor LM93'...                No
Probing for `Winbond W83781D'...                            No
Probing for `Winbond W83782D'...                            No
Probing for `Winbond W83792D'...                            No
Probing for `Winbond W83793R/G'...                          No
Probing for `Winbond W83791SD'...                           No
Probing for `Winbond W83627HF'...                           No
Probing for `Winbond W83627EHF'...                          No
Probing for `Winbond W83627DHG'...                          No
Probing for `Asus AS99127F (rev.1)'...                      No
Probing for `Asus AS99127F (rev.2)'...                      No
Probing for `Asus ASB100 Bach'...                           No
Probing for `Winbond W83L785TS-S'...                        No
Probing for `Analog Devices ADM9240'...                     No
Probing for `Dallas Semiconductor DS1780'...                No
Probing for `National Semiconductor LM81'...                No
Probing for `Analog Devices ADM1026'...                     No
Probing for `Analog Devices ADM1025'...                     No
Probing for `Analog Devices ADM1024'...                     No
Probing for `Analog Devices ADM1029'...                     No
Probing for `Analog Devices ADM1030'...                     No
Probing for `Analog Devices ADM1031'...                     No
Probing for `Analog Devices ADM1022'...                     No
Probing for `Texas Instruments THMC50'...                   No
Probing for `Analog Devices ADM1028'...                     No
Probing for `ITE IT8712F'...                                No
Probing for `SMSC DME1737'...                               No
Probing for `Fintek F75373S/SG'...                          No
Probing for `Fintek F75375S/SP'...                          No
Probing for `Fintek F75387SG/RG'...                         No
Probing for `Winbond W83791D'...                            No
Client found at address 0x44
Probing for `Maxim MAX6633/MAX6634/MAX6635'...              No
Client found at address 0x50
Probing for `Analog Devices ADM1033'...                     No
Probing for `Analog Devices ADM1034'...                     No
Probing for `SPD EEPROM'...                                 Success!
    (confidence 8, driver `eeprom')
Probing for `EDID EEPROM'...                                No
Probing for `Maxim MAX6900'...                              No
Client found at address 0x52
Probing for `Analog Devices ADM1033'...                     No
Probing for `Analog Devices ADM1034'...                     No
Probing for `SPD EEPROM'...                                 Success!
    (confidence 8, driver `eeprom')

Some chips are also accessible through the ISA I/O ports. We have to
write to arbitrary I/O ports to probe them. This is usually safe though.
Yes, you do have ISA I/O ports even if you do not have any ISA slots!
Do you want to scan the ISA I/O ports? (YES/no):
Probing for `National Semiconductor LM78' at 0x290...       No
Probing for `National Semiconductor LM78-J' at 0x290...     No
Probing for `National Semiconductor LM79' at 0x290...       No
Probing for `Winbond W83781D' at 0x290...                   No
Probing for `Winbond W83782D' at 0x290...                   No
Probing for `Silicon Integrated Systems SIS5595'...         No
Probing for `VIA VT82C686 Integrated Sensors'...            No
Probing for `VIA VT8231 Integrated Sensors'...              No
Probing for `IPMI BMC KCS' at 0xca0...                      No
Probing for `IPMI BMC SMIC' at 0xca8...                     No

Some Super I/O chips may also contain sensors. We have to write to
standard I/O ports to probe them. This is usually safe.
Do you want to scan for Super I/O sensors? (YES/no):
Probing for Super-I/O at 0x2e/0x2f
Trying family `ITE'...                                      Yes
Found unknown chip with ID 0x7803
Trying family `National Semiconductor'...                   No
Trying family `SMSC'...                                     Yes
Found `SMSC DME1737 Super IO'
    (no hardware monitoring capabilities)
Trying family `VIA/Winbond/Fintek'...                       No
Probing for Super-I/O at 0x4e/0x4f
Trying family `ITE'...                                      No
Trying family `National Semiconductor'...                   No
Trying family `SMSC'...                                     No
Trying family `VIA/Winbond/Fintek'...                       No

Some CPUs or memory controllers may also contain embedded sensors.
Do you want to scan for them? (YES/no):
AMD K8 thermal sensors...                                   No
Intel Core family thermal sensor...                         Success!
    (driver `coretemp')
Intel AMB FB-DIMM thermal sensor...                         No

Now follows a summary of the probes I have just done.
Just press ENTER to continue:

Driver `eeprom' (should be inserted):
  Detects correctly:
  * Bus `SMBus I801 adapter at 3000'
    Busdriver `i2c-i801', I2C address 0x50
    Chip `SPD EEPROM' (confidence: 8)
  * Bus `SMBus I801 adapter at 3000'
    Busdriver `i2c-i801', I2C address 0x52
    Chip `SPD EEPROM' (confidence: 8)

  EEPROMs are *NOT* sensors! They are data storage chips commonly
  found on memory modules (SPD), in monitors (EDID), or in some
  laptops, for example.

Driver `coretemp' (should be inserted):
  Detects correctly:
  * Chip `Intel Core family thermal sensor' (confidence: 9)

I will now generate the commands needed to load the required modules.
Just press ENTER to continue:

To make the sensors modules behave correctly, add these lines to
/etc/modules.conf:

#----cut here----
# I2C module options
alias char-major-89 i2c-dev
#----cut here----

To load everything that is needed, add this to some /etc/rc* file:

#----cut here----
# I2C adapter drivers
modprobe i2c-i801
# Chip drivers
modprobe eeprom
# Warning: the required module coretemp is not currently installed
# on your system. For status of 2.6 kernel ports check
# http://www.lm-sensors.org/wiki/Devices. If driver is built
# into the kernel, or unavailable, comment out the following line.
modprobe coretemp
# sleep 2 # optional
/usr/local/bin/sensors -s # recommended
#----cut here----

If you have some drivers built into your kernel, the list above will
contain too many modules. Skip the appropriate ones! You really
should try these commands right now to make sure everything is
working properly. Monitoring programs won't work until the needed
modules are loaded.

Do you want to overwrite /etc/sysconfig/lm_sensors? (YES/no):
Copy prog/init/lm_sensors.init to /etc/init.d/lm_sensors
for initialization at boot time.
debian14:~#

```



```

debian14:~# lspci -v
00:00.0 Host bridge: Intel Corporation E7230 Memory Controller Hub
        Subsystem: Intel Corporation Unknown device 3489
        Flags: bus master, fast devsel, latency 0
        Capabilities: [e0] Vendor Specific Information

00:1c.0 PCI bridge: Intel Corporation 82801G (ICH7 Family) PCI Express Port 1 (rev 01) (prog-if 00 [Normal decode])
        Flags: bus master, fast devsel, latency 0
        Bus: primary=00, secondary=01, subordinate=01, sec-latency=0
        Capabilities: [40] Express Root Port (Slot+) IRQ 0
        Capabilities: [80] Message Signalled Interrupts: Mask- 64bit- Queue=0/0 Enable-
        Capabilities: [90] Subsystem: Intel Corporation 82801G (ICH7 Family) PCI Express Port 1
        Capabilities: [a0] Power Management version 2

00:1c.4 PCI bridge: Intel Corporation 82801GR/GH/GHM (ICH7 Family) PCI Express Port 5 (rev 01) (prog-if 00 [Normal decode])
        Flags: bus master, fast devsel, latency 0
        Bus: primary=00, secondary=02, subordinate=02, sec-latency=0
        Capabilities: [40] Express Root Port (Slot+) IRQ 0
        Capabilities: [80] Message Signalled Interrupts: Mask- 64bit- Queue=0/0 Enable-
        Capabilities: [90] Subsystem: Intel Corporation 82801GR/GH/GHM (ICH7 Family) PCI Express Port 5
        Capabilities: [a0] Power Management version 2

00:1c.5 PCI bridge: Intel Corporation 82801GR/GH/GHM (ICH7 Family) PCI Express Port 6 (rev 01) (prog-if 00 [Normal decode])
        Flags: bus master, fast devsel, latency 0
        Bus: primary=00, secondary=03, subordinate=03, sec-latency=0
        I/O behind bridge: 00002000-00002fff
        Memory behind bridge: 88100000-881fffff
        Capabilities: [40] Express Root Port (Slot+) IRQ 0
        Capabilities: [80] Message Signalled Interrupts: Mask- 64bit- Queue=0/0 Enable-
        Capabilities: [90] Subsystem: Intel Corporation 82801GR/GH/GHM (ICH7 Family) PCI Express Port 6
        Capabilities: [a0] Power Management version 2

00:1d.0 USB Controller: Intel Corporation 82801G (ICH7 Family) USB UHCI #1 (rev 01) (prog-if 00 [UHCI])
        Subsystem: Intel Corporation Unknown device 3489
        Flags: bus master, medium devsel, latency 0, IRQ 18
        I/O ports at 3080 [size=32]

00:1d.1 USB Controller: Intel Corporation 82801G (ICH7 Family) USB UHCI #2 (rev 01) (prog-if 00 [UHCI])
        Subsystem: Intel Corporation Unknown device 3489
        Flags: bus master, medium devsel, latency 0, IRQ 19
        I/O ports at 3060 [size=32]

00:1d.2 USB Controller: Intel Corporation 82801G (ICH7 Family) USB UHCI #3 (rev 01) (prog-if 00 [UHCI])
        Subsystem: Intel Corporation Unknown device 3489
        Flags: bus master, medium devsel, latency 0, IRQ 20
        I/O ports at 3040 [size=32]

00:1d.3 USB Controller: Intel Corporation 82801G (ICH7 Family) USB UHCI #4 (rev 01) (prog-if 00 [UHCI])
        Subsystem: Intel Corporation Unknown device 3489
        Flags: bus master, medium devsel, latency 0, IRQ 17
        I/O ports at 3020 [size=32]

00:1d.7 USB Controller: Intel Corporation 82801G (ICH7 Family) USB2 EHCI Controller (rev 01) (prog-if 20 [EHCI])
        Subsystem: Intel Corporation Unknown device 3489
        Flags: bus master, medium devsel, latency 0, IRQ 18
        Memory at 88200400 (32-bit, non-prefetchable) [size=1K]
        Capabilities: [50] Power Management version 2
        Capabilities: [58] Debug port

00:1e.0 PCI bridge: Intel Corporation 82801 PCI Bridge (rev e1) (prog-if 01 [Subtractive decode])
        Flags: bus master, fast devsel, latency 0
        Bus: primary=00, secondary=04, subordinate=04, sec-latency=32
        I/O behind bridge: 00001000-00001fff
        Memory behind bridge: 88000000-880fffff
        Prefetchable memory behind bridge: 0000000080000000-0000000087ffffff
        Capabilities: [50] Subsystem: Intel Corporation Unknown device 3489

00:1f.0 ISA bridge: Intel Corporation 82801GB/GR (ICH7 Family) LPC Interface Bridge (rev 01)
        Subsystem: Intel Corporation Unknown device 3489
        Flags: bus master, medium devsel, latency 0
        Capabilities: [e0] Vendor Specific Information

00:1f.1 IDE interface: Intel Corporation 82801G (ICH7 Family) IDE Controller (rev 01) (prog-if 8a [Master SecP PriP])
        Subsystem: Intel Corporation Unknown device 3489
        Flags: bus master, medium devsel, latency 0, IRQ 20
        I/O ports at <ignored>
        I/O ports at </ignored><ignored>
        I/O ports at </ignored><ignored>
        I/O ports at </ignored><ignored>
        I/O ports at 30b0 [size=16]

00:1f.2 IDE interface: Intel Corporation 82801GB/GR/GH (ICH7 Family) Serial ATA Storage Controller IDE (rev 01) (prog-if 8f [Master SecP SecO PriP PriO])
        Subsystem: Intel Corporation Unknown device 3489
        Flags: bus master, 66MHz, medium devsel, latency 0, IRQ 19
        I/O ports at 30c8 [size=8]
        I/O ports at 30e4 [size=4]
        I/O ports at 30c0 [size=8]
        I/O ports at 30e0 [size=4]
        I/O ports at 30a0 [size=16]
        Memory at 88200000 (32-bit, non-prefetchable) [size=1K]
        Capabilities: [70] Power Management version 2

00:1f.3 SMBus: Intel Corporation 82801G (ICH7 Family) SMBus Controller (rev 01)
        Subsystem: Intel Corporation Unknown device 3489
        Flags: medium devsel, IRQ 19
        I/O ports at 3000 [size=32]

03:00.0 Ethernet controller: Intel Corporation 82573V Gigabit Ethernet Controller (Copper) (rev 03)
        Subsystem: Intel Corporation Unknown device 3489
        Flags: bus master, fast devsel, latency 0, IRQ 16
        Memory at 88100000 (32-bit, non-prefetchable) [size=128K]
        I/O ports at 2000 [size=32]
        Capabilities: [c8] Power Management version 2
        Capabilities: [d0] Message Signalled Interrupts: Mask- 64bit+ Queue=0/0 Enable-
        Capabilities: [e0] Express Endpoint IRQ 0

04:04.0 VGA compatible controller: ATI Technologies Inc ES1000 (rev 02) (prog-if 00 [VGA])
        Subsystem: Intel Corporation Unknown device 3489
        Flags: bus master, stepping, fast Back2Back, medium devsel, latency 32, IRQ 11
        Memory at 80000000 (32-bit, prefetchable) [size=128M]
        I/O ports at 1000 [size=256]
        Memory at 88000000 (32-bit, non-prefetchable) [size=64K]
        Expansion ROM at fffe0000 [disabled] [size=128K]
        Capabilities: [50] Power Management version 2

debian14:~#
</ignored>
```
