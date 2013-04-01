---
layout: post
published: true
title: Accessing Munin nodes through SSH tunnels
permalink: /accessing-munin-nodes-through-ssh-tunnels/
wordpress_id: 416
categories:
- Links
- Linux
- unix
- Firewall system
---
When there is a need to reach one or more hosts behind a non-routing Firewall system (<a href="http://en.wikipedia.org/wiki/%2Anix">Unix or Linux</a> like), you may use SSH tunneling.

The setup is as follows; an SSH connection is established between the Munin server and the in-between system (referred to as 'bouncer'). This connection will tunnel a number of forwarded ports between the local Munin server and the different Munin nodes. The connection will be encrypted between the Munin server and the bouncer, but unencrypted from the bouncer to the Munin nodes.

<strong>Create the SSH connection with the following command:</strong>

```
ssh -L 5001:Server-A:4949 -L 5002:Server-B:4949 -L 5003:Server-C:4949 user@bouncer
```


Using this ssh command line will establish connection to the bouncer and map the ports, localport 5001 to forarded to Server-A's port 4949 and so on and so forth.

If you have many tunnels to a bunch of servers in one or more DMZs you may want a mechanism, that takes care that the tunnel is up and running. Even if a tunnel is running yet, the connection can drop some day (a short-term network problem, a reboot of the munin-node etc). In this case, this machnism must restart the tunnel soon. The best way to overcome this problem is to use autossh, which is a program that starts and monitors ssh connections and restarting them as necessary if a connection dies or traffic stops passing. Thereby the autossh ensures constant tunnel connection.

To use autossh for establishing the connection, type this:

```
autossh -M 29001 -f -L 5001:Server-A:4949 -L 5002:Server-B:4949 -L 5003:Server-C:4949 user@bouncer
```


<strong>Startup</strong>
Put the autossh commandline into your /etc/rc.local or like to initialize the tunnel at startup


<strong>To use this setup the munin.conf must be configured accordingly:</strong>

```

[Server-A]
  address 127.0.0.1
  port 5001
  use_node_name yes

[Server-B]
  address 127.0.0.1
  port 5002
  use_node_name yes

[Server-C]
  address 127.0.0.1
  port 5003
  use_node_name yes

```



