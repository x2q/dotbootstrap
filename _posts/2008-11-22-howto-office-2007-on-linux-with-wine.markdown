---
layout: post
published: true
title: ! 'Howto: Office 2007 on Linux with Wine'
permalink: /howto-office-2007-on-linux-with-wine/
wordpress_id: 692
categories:
- Linux
- Vista
- Ubuntu
- Microsoft
- wine
- office 2007
- OpenOffice
- office
- Windows Vista
- Windows XP
- install
- fonts
- Windows Server 2003
- Microsoft Windows
- GUI
- item inspector
- Las Vegas
- Windows XP Office
- wine office 2007
- office 2007 wine
- wine outlook 2007
- outlook 2007 wine
- winetricks office 2007
---


Microsoft Office 2007 is the most recent Windows version of the Microsoft Office system, Microsoft's productivity suite. Formerly known as Office 12 in the initial stages of its beta cycle, it was released to volume license customers on November 30, 2006 and made available to retail customers on January 30, 2007.

<strong>New Features in Office 2007</strong>
Office 2007 contains a number of new features, the most notable of which is the entirely new graphical user interface called the Fluent User Interface (initially referred to as the Ribbon UI), replacing the menus and toolbars that have been the cornerstone of Office since its inception with a tabbed toolbar, known as the Ribbon. Office 2007 requires Windows XP with Service Pack 2 or 3, Windows Server 2003 with Service Pack 1 or higher, or Windows Vista.

The 'Ribbon User Interface' is a task-orientated Graphical User Interface (GUI). It features a central menu button, widely known as the 'Office Button'. The Ribbon Interface has been rumored to be introduced into Microsoft Office 14.

The new user interface (UI), officially known as Microsoft Office Fluent, has been implemented in the core Microsoft Office applications: Word, Excel, PowerPoint, Access, and in the item inspector used to create or edit individual items in Outlook. These applications have been selected for the UI overhaul because they center around document authoring. The rest of the applications in the suite will also be upgraded to the new UI in subsequent versions. The default font used in this edition is Calibri. Original prototypes of the new user interface were revealed at MIX 2008 in Las Vegas.

<strong>Getting Wine Ready for Office 2007</strong>

<strong>Wine Configuration</strong>
The following guide is based on a clean configuration directory and running in a 1024x768 virtual desktop.


```

Wine version used:
wine-1.1.9
Windows version emulated:
Windows XP
Office version:
Microsoft Office 2007

```


Download and install the latest Wine available by following this <a href="http://www.winehq.org/download/debian">guide</a>.


```

$ winecfg

```


When the configuration dialog appears set the virtual desktop in the graphics tab and click OK.

Then download winetricks using wget:

```

$ wget http://www.kegel.com/wine/winetricks

```



```

sh winetricks msxml3 dotnet20 gdiplus riched20 riched30 vcrun2005sp1 allfonts

```


<strong>Installing Microsoft Office 2007</strong>
Office 2007 requires a libraries, which are not included in a plain Wine-installation. These libraries could be obtained from <a href="http://www.codeweavers.com/products/cxgames/">CrossOver Games</a>, which is a derived version of Wine made to support games under Linux.

Download and install <a href="http://www.codeweavers.com/products/cxgames/">CrossOver Games</a> either by hand or by using the official Ubuntu or Debian package.


After the install then

Copy rpcrt4.dll.so into Wine:

```

$ sudo cp /opt/cxgames/lib/wine/rpcrt4.dll.so .wine/drive_c/windows/system32/

```


Rename the native Wine-dll version:

```

$ sudo mv .wine/drive_c/windows/system32/rpcrt4.dll .wine/drive_c/windows/system32/rpcrt4.dll.bak

```


Rename CrossOver Games version into the original name:

```

$ sudo mv .wine/drive_c/windows/system32/rpcrt4.dll.so .wine/drive_c/windows/system32/rpcrt4.dll

```


Moreover you will need to rename msxml3.dll into *.bak too:

```

$ sudo mv .wine/drive_c/windows/system32/msxml3.dll .wine/drive_c/windows/system32/msxml3.dll.bak

```


After the renaming it is time to run winecfg again and set <strong>msxml3.dll</strong> and <strong>rpcrt4.dll</strong> to "native windows" select save and exit.

Now it is time to mount the Office 2007 cd media and start the actual Office 2007 installation.

```

$ sudo mount -o loop -o unhide Office-2007.iso /mnt

```


Now cd into the mounted directory

```

$ cd /mnt
$ wine setup.exe

```

Type the serial number and click install.

<br />

<br />

[youtube]yDmc4fG2AJM&hl[/youtube]
