---
layout: post
published: true
title: Howto Install Carwhisperer on Ubuntu 9.10
permalink: /howto-install-carwhisperer-on-ubuntu-9-10/
wordpress_id: 895
categories:
- News
- Linux
- Ubuntu
- Crack
- hack
- bluetooth
- eavesdrop
- headset
- car audio
- handset
- carwhisperer
- pushy Audi driver
- car whisperer
---


<a href="http://trifinite.org/trifinite_stuff_carwhisperer.html">Carwhisperer</a> is a new tool, which allows people equipped with a Linux Laptop and a directional antenna to inject audio to, and record audio from bypassing cars that have an unconnected Bluetooth handsfree unit running. Since many manufacturers use a standard passkey which often is the only authentication that is needed to connect.

This tool allows to interact with other drivers when travelling or maybe used in order to talk to that pushy Audi driver right behind you ;) . It also allows to eavesdrop conversations in the inside of the car by accessing the microphone.



<strong>Installation Guidelines</strong>

<strong>Install libbluetooth-dev </strong>

```

sudo aptitude install libbluetooth-dev

```


<strong>Download Carwhisperer, untar and compile carwhisperer</strong>

```

wget http://trifinite.org/Downloads/carwhisperer-0.2.tar.gz
tar zxvf carwhisperer-0.2.tar.gz
cd carwhisperer-0.2
make

```


<strong>Download simple passkey agent</strong>
A simple passkey agent is needed, a passkey agent, which is written to automatically return pin code 0000 to all bluetooth pin requests.


```

wget https://gist.github.com/x2q/5285011/raw/simple-agent
# Kill the existing passkey agent
pkill -9 bluetooth-applet
chmod +x simple-agent
./simple-agent

```


Run Carwhisperer

```

./cw_scanner

```
