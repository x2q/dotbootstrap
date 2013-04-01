---
layout: post
published: true
title: Brother Printer Drivers and Ubuntu Linux 64 Bit
permalink: /brother-printer-drivers-and-ubuntu-linux-64-bit/
wordpress_id: 865
categories:
- News
- Linux
- Ubuntu
- Printers
- brother
- printer
- 64-bit
- laser
- LPR driver
---


Ubuntu is born with packages for Brother printers.

The following packages is available:

brother-cups-wrapper-ac - Cups Wrapper drivers for ac brother printers
brother-cups-wrapper-bh7 - Cups Wrapper drivers for bh7 brother printers
brother-cups-wrapper-common - Common files for Brother cups wrapper packages
brother-cups-wrapper-extra - Cups Wrapper drivers for extra brother printers
brother-cups-wrapper-laser - Cups Wrapper drivers for laser brother printers
brother-cups-wrapper-laser1 - Cups Wrapper drivers for laser1 brother printers
brother-cups-wrapper-mfc9420cn - Cups Wrapper drivers for mfc9420cn brother printers
brother-lpr-drivers-ac  - LPR drivers for ac brother printers
brother-lpr-drivers-bh7 - LPR drivers for bh7 brother printers
brother-lpr-drivers-common - Common files for brother-lpr-drivers packages
brother-lpr-drivers-extra - LPR drivers for extra brother printers
brother-lpr-drivers-laser - LPR drivers for laser brother printers
brother-lpr-drivers-laser1 - LPR drivers for laser1 brother printers
brother-lpr-drivers-mfc9420cn- LPR driver for mfc9420cn brother printer

brother-cups-wrapper contains the 5 existing cups wrapper from Brother, under a PLG License.

brother-lpr-drivers contains all the LPR drivers, distributed under the Brother Software Open License Agreement

The -extra package contains all drivers that does not have a opensource tarballs. These drivers use the same binary cups wrapper as bh7 package.

The -common package contains shared files between various packages. -common only prevent conflicts for bh7/extra packages files and laser/laser1.
