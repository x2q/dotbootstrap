---
layout: post
published: true
title: Java and C# Client Server Socket Programming
permalink: /java-and-c-client-server-socket-programming/
wordpress_id: 455
categories:
- News
- Open Standards
- Open Source
- Java
- C++
- public class java_server
- System.IO
- System.Net.
- c# client server
- c# java socket
- java c# socket
---



```

C# client namespaces
----------------
1.System
2.System.Net.Sockets
3.System.IO;

java packages
--------------
1.java.net
2.java.io

```



<strong>Java server Application</strong>
<code lang=Java>
import java.net.*;
import java.io.*;
public class java_server
{
public static void main(String h[])
    {
     try
     {
     ServerSocket ss=new ServerSocket(1800);
     Socket s=ss.accept();
     System.out.println("Client Accepted");
     BufferedReader br=new BufferedReader(new 
InputStreamReader(s.getInputStream()));
  System.out.println(br.readLine());
  PrintWriter wr=new PrintWriter(new 
OutputStreamWriter(s.getOutputStream()),true);
  wr.println("Welcome to Socket Programming");
  }catch(Exception e){System.out.println(e);}
   }
   }

```


<strong>Compile using</strong>

```
javac java_server.java
```



<strong>C# client Application</strong>


<code lang=c#>
using System;
using System.Net.Sockets;
using System.IO;
class csharp_client
{
public static void Main(string[] args)
{
try{
TcpClient tc=new TcpClient("server",1800);// in the place of server, enter 
your java server's hostname or Ip
Console.WriteLine("Server invoked");
NetworkStream ns=tc.GetStream();
StreamWriter sw=new StreamWriter(ns);
sw.WriteLine("My name is Pramod.A");
sw.Flush();
StreamReader sr=new StreamReader(ns);
Console.WriteLine(sr.ReadLine());
}catch(Exception e){Console.WriteLine(e);}
          }

}

```



<strong>Compile using the command</strong>

```
csc /r:System.dll  csharp_client.cs
```


<strong>After compilation, run the java server first</strong>

```
java java_server
```


<strong>Then run the c# client application</strong>

```
csharp_client
```
