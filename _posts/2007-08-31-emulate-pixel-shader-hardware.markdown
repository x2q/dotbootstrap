---
layout: post
published: true
title: Emulate Pixel Shader Hardware
permalink: /emulate-pixel-shader-hardware/
wordpress_id: 498
categories:
- News
- Vista
- Windows
- Intel
- emulation
- DirectX
- xp
- wine
- google
- pixel shader 3 0 emulator
- pixel shader 3 emulator
- pixel shader 2 0 emulator
- emulate pixel shader
- emulate pixel shader 3
---


Today I tried to run the new Settlers II - 10 Anniversary on my Lenovo laptop, but it was unable to run due to the fact that my laptop's integrated graphics card (a <a href="http://en.wikipedia.org/wiki/Intel_GMA">Intel i945GM</a>) doesn't support Pixel Shader 2.0. I have then searched Google for a software based Pixel Shader - and I actually found one called <a href="http://transgaming.com/index.php?module=ContentExpress&amp;file=index&amp;func=display&amp;ceid=8">SwiftShader</a> from a company called <a href="http://transgaming.com/">TransGaming</a>. SwiftShader features all DirectX Pixel Shader 1.1 calls and most of the DirectX 2.0 calls, but not all of them.

It's easy to install SwiftShader. Just copy the two DirectX 3D related files: d3d8.dll and d3d9.dll into the root of the Direct 3D game or application and you should be up and running.

<img id="image285" src="http://lh3.ggpht.com/-SVx49cuiPac/UVl_I0oCjpI/AAAAAAAAFuE/uMUO0eC6NZg/swiftscreenshot-big.jpg" alt="Software based Renderer - (Emulated) Pixel Shader 2.0" />

