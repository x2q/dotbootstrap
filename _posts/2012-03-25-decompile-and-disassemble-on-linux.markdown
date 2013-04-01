---
layout: post
published: true
title: Decompile and Disassemble on Linux
permalink: /decompile-and-disassemble-on-linux/
wordpress_id: 949
categories:
- Linux
- Debian
- decompile
- disassemble
- Bastard Disassembler
- objdump
- gdb
- x86dis
- ldasm
---
In essence, a disassembler is the exact opposite of an assembler. Where an assembler converts code written in an assembly language into binary machine code, a disassembler reverses the process and attempts to recreate the assembly code from the binary machine code.
Since most assembly languages have a one-to-one correspondence with underlying machine instructions, the process of disassembly is relatively straight-forward, and a basic disassembler can often be implemented simply by reading in bytes, and performing a table lookup. Of course, disassembly has its own problems and pitfalls, and they are covered later in this chapter.
Many disassemblers have the option to output assembly language instructions in Intel, AT&amp;T, HLA syntax etc.
<h2>Linux Disassemblers Available</h2>
<dl><dt>Bastard Disassembler</dt><dd>The Bastard disassembler is a powerful, scriptable disassembler for Linux and FreeBSD.</dd><dd><a href="http://bastard.sourceforge.net/" rel="nofollow" target="_blank">http://bastard.sourceforge.net/</a></dd><dd></dd></dl><dl><dt>udis86</dt><dd>Disassembler Library for x86 and x86-64</dd><dd><a href="http://udis86.sourceforge.net/" rel="nofollow" target="_blank">http://udis86.sourceforge.net/</a></dd><dd></dd></dl><dl><dt>ciasdis</dt></dl><dl><dd>The official name of ciasdis is computer_intelligence_assembler_disassembler. This Forth-based tool allows to incrementally and interactively build knowledge about a code body. It is unique that all disassembled code can be re-assembled to the exact same code. Processors are 8080, 6809, 8086, 80386, Pentium I en DEC Alpha. A scripting facility aids in analyzing Elf and MSDOS headers and makes this tool extendable. The Pentium I ciasdis is available as a binary image, others are in source form, loadable onto lina Forth, available from the same site.</dd><dd><a href="http://home.hccnet.nl/a.w.m.van.der.horst/ciasdis.html" rel="nofollow" target="_blank">http://home.hccnet.nl/a.w.m.van.der.horst/ciasdis.html</a></dd><dd></dd></dl><dl><dt>objdump&nbsp;</dt><dd>comes standard, and is typically used for general inspection of binaries. Pay attention to the relocation option and the dynamic symbol table option.</dd></dl><dl><dt></dt><dt>gdb&nbsp;</dt><dd>comes standard, as a debugger, but is very often used for disassembly. If you have loose hex dump data that you wish to disassemble, simply enter it (interactively) over top of something else or compile it into a program as a string like so: char foo[] = {0x90, 0xcd, 0x80, 0x90, 0xcc, 0xf1, 0x90};</dd></dl><dl><dt></dt><dt>lida linux interactive disassembler</dt><dd>an interactive disassembler with some special functions like a crypto analyzer. Displays string data references, does code flow analysis, and does not rely on objdump. Utilizes the Bastard disassembly library for decoding single opcodes. The project was started in 2004 and remains dormant to this day.</dd><dd><a href="http://lida.sourceforge.net/" rel="nofollow" target="_blank">http://lida.sourceforge.net</a></dd></dl><dl><dt></dt><dt>dissy&nbsp;</dt><dd>This program is a interactive disassembler that uses objdump.</dd><dd><a href="http://code.google.com/p/dissy/" rel="nofollow" target="_blank">http://code.google.com/p/dissy/</a></dd></dl><dl><dt></dt><dt>x86dis&nbsp;</dt><dd>This program can be used to display binary streams such as the boot sector or other unstructured binary files.</dd></dl><dl><dt></dt><dt>ldasm</dt><dd>LDasm (Linux Disassembler) is a Perl/Tk-based GUI for objdump/binutils that tries to imitate the 'look and feel' of W32Dasm. It searches for cross-references (e.g. strings), converts the code from GAS to a MASM-like style, traces programs and much more. Comes along with PTrace, a process-flow-logger.</dd><dd><a href="http://www.feedface.com/projects/ldasm.html" rel="nofollow" target="_blank">http://www.feedface.com/projects/ldasm.html</a></dd></dl>
<h2></h2>
<h2>Example with x86dis</h2>
First we compile hello.c -- The most famous program of them all using gcc.


```

/* hello.c -- The most famous program of them all ..
*/

#include

int main(void) {
printf("Hello World!\n");
// return 0;
}
```

```
gcc -o hello hello.c
```


Then we dissamble the binary hello file using x86dis

```

$ x86dis -e 0 -s intel < hello
00000000 7F 45 jg 0x00000047
00000002 4C dec esp
00000003 46 inc esi
00000004 02 01 add al, [ecx]
00000006 01 00 add [eax], eax
00000008 00 00 add [eax], al
0000000A 00 00 add [eax], al
0000000C 00 00 add [eax], al
0000000E 00 00 add [eax], al
00000010 02 00 add al, [eax]
00000012 3E 00 01 add ds:[ecx], al
00000015 00 00 add [eax], al
00000017 00 10 add [eax], dl
00000019 04 40 add al, 0x40
0000001B 00 00 add [eax], al
0000001D 00 00 add [eax], al
0000001F 00 40 00 add [eax+], al
00000022 00 00 add [eax], al
00000024 00 00 add [eax], al
00000026 00 00 add [eax], al
00000028 48 dec eax
00000029 11 00 adc [eax], eax
0000002B 00 00 add [eax], al
0000002D 00 00 add [eax], al
0000002F 00 00 add [eax], al
00000031 00 00 add [eax], al
00000033 00 40 00 add [eax+], al
00000036 38 00 cmp [eax], al
00000038 09 00 or [eax], eax
0000003A 40 inc eax
0000003B 00 1E add [esi], bl
0000003D 00 1B add [ebx], bl
0000003F 00 06 add [esi], al
00000041 00 00 add [eax], al
00000043 00 05 00 00 00 40 add [0x40000000], al
00000049 00 00 add [eax], al
0000004B 00 00 add [eax], al
0000004D 00 00 add [eax], al
0000004F 00 40 00 add [eax+], al
00000052 40 inc eax
00000053 00 00 add [eax], al
00000055 00 00 add [eax], al
00000057 00 40 00 add [eax+], al
0000005A 40 inc eax
0000005B 00 00 add [eax], al
0000005D 00 00 add [eax], al
0000005F 00 F8 add al, bh
00000061 01 00 add [eax], eax
00000063 00 00 add [eax], al
00000065 00 00 add [eax], al
00000067 00 F8 add al, bh
00000069 01 00 add [eax], eax
0000006B 00 00 add [eax], al
0000006D 00 00 add [eax], al
0000006F 00 08 add [eax], cl
00000071 00 00 add [eax], al
00000073 00 00 add [eax], al
00000075 00 00 add [eax], al
00000077 00 03 add [ebx], al
00000079 00 00 add [eax], al
0000007B 00 04 00 add [eax+eax], al
0000007E 00 00 add [eax], al
00000080 38 02 cmp [edx], al
00000082 00 00 add [eax], al
00000084 00 00 add [eax], al
00000086 00 00 add [eax], al
00000088 38 02 cmp [edx], al
0000008A 40 inc eax
0000008B 00 00 add [eax], al
0000008D 00 00 add [eax], al
0000008F 00 38 add [eax], bh
00000091 02 40 00 add al, [eax+]
00000094 00 00 add [eax], al
00000096 00 00 add [eax], al
00000098 1C 00 sbb al, 0x00
0000009A 00 00 add [eax], al
0000009C 00 00 add [eax], al
0000009E 00 00 add [eax], al
000000A0 1C 00 sbb al, 0x00
000000A2 00 00 add [eax], al
000000A4 00 00 add [eax], al
000000A6 00 00 add [eax], al
000000A8 01 00 add [eax], eax
000000AA 00 00 add [eax], al
000000AC 00 00 add [eax], al
000000AE 00 00 add [eax], al
000000B0 01 00 add [eax], eax
000000B2 00 00 add [eax], al
000000B4 05 00 00 00 00 add eax, 0x00000000
000000B9 00 00 add [eax], al
000000BB 00 00 add [eax], al
000000BD 00 00 add [eax], al
000000BF 00 00 add [eax], al
000000C1 00 40 00 add [eax+], al
000000C4 00 00 add [eax], al
000000C6 00 00 add [eax], al
000000C8 00 00 add [eax], al
000000CA 40 inc eax
000000CB 00 00 add [eax], al
000000CD 00 00 add [eax], al
000000CF 00 DC add ah, bl
000000D1 06 push es
000000D2 00 00 add [eax], al
000000D4 00 00 add [eax], al
000000D6 00 00 add [eax], al
000000D8 DC 06 fadd [esi]
000000DA 00 00 add [eax], al
000000DC 00 00 add [eax], al
000000DE 00 00 add [eax], al
000000E0 00 00 add [eax], al
000000E2 20 00 and [eax], al
000000E4 00 00 add [eax], al
000000E6 00 00 add [eax], al
000000E8 01 00 add [eax], eax
000000EA 00 00 add [eax], al
000000EC 06 push es
000000ED 00 00 add [eax], al
000000EF 00 28 add [eax], ch
000000F1 0E push cs
000000F2 00 00 add [eax], al
000000F4 00 00 add [eax], al
000000F6 00 00 add [eax], al
000000F8 28 0E sub [esi], cl
000000FA 60 pusha
000000FB 00 00 add [eax], al
000000FD 00 00 add [eax], al
000000FF 00 28 add [eax], ch
00000101 0E push cs
00000102 60 pusha
00000103 00 00 add [eax], al
00000105 00 00 add [eax], al
00000107 00 F8 add al, bh
00000109 01 00 add [eax], eax
0000010B 00 00 add [eax], al
0000010D 00 00 add [eax], al
0000010F 00 08 add [eax], cl
00000111 02 00 add al, [eax]
00000113 00 00 add [eax], al
00000115 00 00 add [eax], al
00000117 00 00 add [eax], al
00000119 00 20 add [eax], ah
0000011B 00 00 add [eax], al
0000011D 00 00 add [eax], al
0000011F 00 02 add [edx], al
00000121 00 00 add [eax], al
00000123 00 06 add [esi], al
00000125 00 00 add [eax], al
00000127 00 50 0E add [eax+0xE], dl
0000012A 00 00 add [eax], al
0000012C 00 00 add [eax], al
0000012E 00 00 add [eax], al
00000130 50 push eax
00000131 0E push cs
00000132 60 pusha
00000133 00 00 add [eax], al
00000135 00 00 add [eax], al
00000137 00 50 0E add [eax+0xE], dl
0000013A 60 pusha
0000013B 00 00 add [eax], al
0000013D 00 00 add [eax], al
0000013F 00 90 01 00 00 00 add [eax+0x1], dl
00000145 00 00 add [eax], al
00000147 00 90 01 00 00 00 add [eax+0x1], dl
0000014D 00 00 add [eax], al
0000014F 00 08 add [eax], cl
00000151 00 00 add [eax], al
00000153 00 00 add [eax], al
00000155 00 00 add [eax], al
00000157 00 04 00 add [eax+eax], al
0000015A 00 00 add [eax], al
0000015C 04 00 add al, 0x00
0000015E 00 00 add [eax], al
00000160 54 push esp
00000161 02 00 add al, [eax]
00000163 00 00 add [eax], al
00000165 00 00 add [eax], al
00000167 00 54 02 40 add [edx+eax+0x40], dl
0000016B 00 00 add [eax], al
0000016D 00 00 add [eax], al
0000016F 00 54 02 40 add [edx+eax+0x40], dl
00000173 00 00 add [eax], al
00000175 00 00 add [eax], al
00000177 00 44 00 00 add [eax+eax+], al
0000017B 00 00 add [eax], al
0000017D 00 00 add [eax], al
0000017F 00 44 00 00 add [eax+eax+], al
00000183 00 00 add [eax], al
00000185 00 00 add [eax], al
00000187 00 04 00 add [eax+eax], al
0000018A 00 00 add [eax], al
0000018C 00 00 add [eax], al
0000018E 00 00 add [eax], al
00000190 50 push eax
00000191 E5 74 in al, 0x74
00000193 64 04 00 add al, 0x00
00000196 00 00 add [eax], al
00000198 0C 06 or al, 0x06
0000019A 00 00 add [eax], al
0000019C 00 00 add [eax], al
0000019E 00 00 add [eax], al
000001A0 0C 06 or al, 0x06
000001A2 40 inc eax
000001A3 00 00 add [eax], al
000001A5 00 00 add [eax], al
000001A7 00 0C 06 add [esi+eax], cl
000001AA 40 inc eax
000001AB 00 00 add [eax], al
000001AD 00 00 add [eax], al
000001AF 00 2C 00 add [eax+eax], ch
000001B2 00 00 add [eax], al
000001B4 00 00 add [eax], al
000001B6 00 00 add [eax], al
000001B8 2C 00 sub al, 0x00
000001BA 00 00 add [eax], al
000001BC 00 00 add [eax], al
000001BE 00 00 add [eax], al
000001C0 04 00 add al, 0x00
000001C2 00 00 add [eax], al
000001C4 00 00 add [eax], al
000001C6 00 00 add [eax], al
000001C8 51 push ecx
000001C9 E5 74 in al, 0x74
000001CB 64 06 push es
000001CD 00 00 add [eax], al
000001CF 00 00 add [eax], al
000001D1 00 00 add [eax], al
000001D3 00 00 add [eax], al
000001D5 00 00 add [eax], al
000001D7 00 00 add [eax], al
000001D9 00 00 add [eax], al
000001DB 00 00 add [eax], al
000001DD 00 00 add [eax], al
000001DF 00 00 add [eax], al
000001E1 00 00 add [eax], al
000001E3 00 00 add [eax], al
000001E5 00 00 add [eax], al
000001E7 00 00 add [eax], al
000001E9 00 00 add [eax], al
000001EB 00 00 add [eax], al
000001ED 00 00 add [eax], al
000001EF 00 00 add [eax], al
000001F1 00 00 add [eax], al
000001F3 00 00 add [eax], al
000001F5 00 00 add [eax], al
000001F7 00 08 add [eax], cl
000001F9 00 00 add [eax], al
000001FB 00 00 add [eax], al
000001FD 00 00 add [eax], al
000001FF 00 52 E5 add [edx-0x1B], dl
00000202 74 64 jz 0x00000268
00000268 02 00 add al, [eax]
0000026A 00 00 add [eax], al
0000026C 06 push es
0000026D 00 00 add [eax], al
0000026F 00 18 add [eax], bl
00000271 00 00 add [eax], al
00000273 00 04 00 add [eax+eax], al
00000276 00 00 add [eax], al
00000278 14 00 adc al, 0x00
0000027A 00 00 add [eax], al
0000027C 03 00 add eax, [eax]
0000027E 00 00 add [eax], al
00000280 47 inc edi
00000281 4E dec esi
00000282 55 push ebp
00000283 00 B3 7B 8F 7D 1D add [ebx+0x1D7D8F7B], dh
00000289 1F pop ds
0000028A 19 A7 98 A2 38 EA sbb [edi-0x15C75D68], esp
00000290 D3 F7 sal edi, cl
00000292 97 xchg eax, edi
00000293 9C pushf
00000294 12 ED adc ch, ch
00000296 41 inc ecx
00000297 D1 01 rol [ecx], 0x00000001
00000299 00 00 add [eax], al
0000029B 00 01 add [ecx], al
0000029D 00 00 add [eax], al
0000029F 00 01 add [ecx], al
000002A1 00 00 add [eax], al
000002A3 00 00 add [eax], al
000002A5 00 00 add [eax], al
000002A7 00 00 add [eax], al
000002A9 00 00 add [eax], al
000002AB 00 00 add [eax], al
000002AD 00 00 add [eax], al
000002AF 00 00 add [eax], al
000002B1 00 00 add [eax], al
000002B3 00 00 add [eax], al
000002B5 00 00 add [eax], al
000002B7 00 00 add [eax], al
000002B9 00 00 add [eax], al
000002BB 00 00 add [eax], al
000002BD 00 00 add [eax], al
000002BF 00 00 add [eax], al
000002C1 00 00 add [eax], al
000002C3 00 00 add [eax], al
000002C5 00 00 add [eax], al
000002C7 00 00 add [eax], al
000002C9 00 00 add [eax], al
000002CB 00 00 add [eax], al
000002CD 00 00 add [eax], al
000002CF 00 1A add [edx], bl
000002D1 00 00 add [eax], al
000002D3 00 12 add [edx], dl
000002D5 00 00 add [eax], al
000002D7 00 00 add [eax], al
000002D9 00 00 add [eax], al
000002DB 00 00 add [eax], al
000002DD 00 00 add [eax], al
000002DF 00 00 add [eax], al
000002E1 00 00 add [eax], al
000002E3 00 00 add [eax], al
000002E5 00 00 add [eax], al
000002E7 00 1F add [edi], bl
000002E9 00 00 add [eax], al
000002EB 00 12 add [edx], dl
000002ED 00 00 add [eax], al
000002EF 00 00 add [eax], al
000002F1 00 00 add [eax], al
000002F3 00 00 add [eax], al
000002F5 00 00 add [eax], al
000002F7 00 00 add [eax], al
000002F9 00 00 add [eax], al
000002FB 00 00 add [eax], al
000002FD 00 00 add [eax], al
000002FF 00 01 add [ecx], al
00000301 00 00 add [eax], al
00000303 00 20 add [eax], ah
00000305 00 00 add [eax], al
00000307 00 00 add [eax], al
00000309 00 00 add [eax], al
0000030B 00 00 add [eax], al
0000030D 00 00 add [eax], al
0000030F 00 00 add [eax], al
00000311 00 00 add [eax], al
00000313 00 00 add [eax], al
00000315 00 00 add [eax], al
00000317 00 00 add [eax], al
00000319 5F pop edi
0000031A 5F pop edi
0000031B 67 6D ins es:[edi], edx
0000031D 6F outs edx, ds:[esi]
0000031E 6E outs dl, ds:[esi]
0000031F 5F pop edi
00000320 73 74 jnc 0x00000396
00000396 00 00 add [eax], al
00000398 00 10 add [eax], dl
0000039A 60 pusha
0000039B 00 00 add [eax], al
0000039D 00 00 add [eax], al
0000039F 00 07 add [edi], al
000003A1 00 00 add [eax], al
000003A3 00 01 add [ecx], al
000003A5 00 00 add [eax], al
000003A7 00 00 add [eax], al
000003A9 00 00 add [eax], al
000003AB 00 00 add [eax], al
000003AD 00 00 add [eax], al
000003AF 00 08 add [eax], cl
000003B1 10 60 00 adc [eax+], ah
000003B4 00 00 add [eax], al
000003B6 00 00 add [eax], al
000003B8 07 pop es
000003B9 00 00 add [eax], al
000003BB 00 02 add [edx], al
000003BD 00 00 add [eax], al
000003BF 00 00 add [eax], al
000003C1 00 00 add [eax], al
000003C3 00 00 add [eax], al
000003C5 00 00 add [eax], al
000003C7 00 48 83 add [eax-0x7D], cl
000003CA EC in al, dx
000003CB 08 E8 or al, ch
000003CD 6B 00 00 imul eax, [eax], 0x00
000003D0 00 E8 add al, ch
000003D2 FA cli
000003D3 00 00 add [eax], al
000003D5 00 E8 add al, ch
000003D7 D5 01 aad 0x01
000003D9 00 00 add [eax], al
000003DB 48 dec eax
000003DC 83 C4 08 add esp, 0x08
000003DF C3 ret
00000322 61 popa
00000323 72 74 jc 0x00000399
00000399 10 60 00 adc [eax+], ah
0000039C 00 00 add [eax], al
0000039E 00 00 add [eax], al
000003A0 07 pop es
000003A1 00 00 add [eax], al
000003A3 00 01 add [ecx], al
000003A5 00 00 add [eax], al
000003A7 00 00 add [eax], al
000003A9 00 00 add [eax], al
000003AB 00 00 add [eax], al
000003AD 00 00 add [eax], al
000003AF 00 08 add [eax], cl
000003B1 10 60 00 adc [eax+], ah
000003B4 00 00 add [eax], al
000003B6 00 00 add [eax], al
000003B8 07 pop es
000003B9 00 00 add [eax], al
000003BB 00 02 add [edx], al
000003BD 00 00 add [eax], al
000003BF 00 00 add [eax], al
000003C1 00 00 add [eax], al
000003C3 00 00 add [eax], al
000003C5 00 00 add [eax], al
000003C7 00 48 83 add [eax-0x7D], cl
000003CA EC in al, dx
000003CB 08 E8 or al, ch
000003CD 6B 00 00 imul eax, [eax], 0x00
000003D0 00 E8 add al, ch
000003D2 FA cli
000003D3 00 00 add [eax], al
000003D5 00 E8 add al, ch
000003D7 D5 01 aad 0x01
000003D9 00 00 add [eax], al
000003DB 48 dec eax
000003DC 83 C4 08 add esp, 0x08
000003DF C3 ret
00000325 5F pop edi
00000326 5F pop edi
00000327 00 6C 69 62 add [ecx+ebp*2+0x62], ch
0000032B 63 2E arpl [esi], bp
0000032D 73 6F jnc 0x0000039E
0000039E 00 00 add [eax], al
000003A0 07 pop es
000003A1 00 00 add [eax], al
000003A3 00 01 add [ecx], al
000003A5 00 00 add [eax], al
000003A7 00 00 add [eax], al
000003A9 00 00 add [eax], al
000003AB 00 00 add [eax], al
000003AD 00 00 add [eax], al
000003AF 00 08 add [eax], cl
000003B1 10 60 00 adc [eax+], ah
000003B4 00 00 add [eax], al
000003B6 00 00 add [eax], al
000003B8 07 pop es
000003B9 00 00 add [eax], al
000003BB 00 02 add [edx], al
000003BD 00 00 add [eax], al
000003BF 00 00 add [eax], al
000003C1 00 00 add [eax], al
000003C3 00 00 add [eax], al
000003C5 00 00 add [eax], al
000003C7 00 48 83 add [eax-0x7D], cl
000003CA EC in al, dx
000003CB 08 E8 or al, ch
000003CD 6B 00 00 imul eax, [eax], 0x00
000003D0 00 E8 add al, ch
000003D2 FA cli
000003D3 00 00 add [eax], al
000003D5 00 E8 add al, ch
000003D7 D5 01 aad 0x01
000003D9 00 00 add [eax], al
000003DB 48 dec eax
000003DC 83 C4 08 add esp, 0x08
000003DF C3 ret
0000032F 2E 36 00 70 75 add ds:[eax+0x75], dh
00000334 74 73 jz 0x000003A9
000003A9 00 00 add [eax], al
000003AB 00 00 add [eax], al
000003AD 00 00 add [eax], al
000003AF 00 08 add [eax], cl
000003B1 10 60 00 adc [eax+], ah
000003B4 00 00 add [eax], al
000003B6 00 00 add [eax], al
000003B8 07 pop es
000003B9 00 00 add [eax], al
000003BB 00 02 add [edx], al
000003BD 00 00 add [eax], al
000003BF 00 00 add [eax], al
000003C1 00 00 add [eax], al
000003C3 00 00 add [eax], al
000003C5 00 00 add [eax], al
000003C7 00 48 83 add [eax-0x7D], cl
000003CA EC in al, dx
000003CB 08 E8 or al, ch
000003CD 6B 00 00 imul eax, [eax], 0x00
000003D0 00 E8 add al, ch
000003D2 FA cli
000003D3 00 00 add [eax], al
000003D5 00 E8 add al, ch
000003D7 D5 01 aad 0x01
000003D9 00 00 add [eax], al
000003DB 48 dec eax
000003DC 83 C4 08 add esp, 0x08
000003DF C3 ret
00000336 00 5F 5F add [edi+0x5F], bl
00000339 6C ins es:[edi], dl
0000033A 69 62 63 5F 73 74 61 imul esp, [edx+0x63], 0x6174735F
00000341 72 74 jc 0x000003B7
000003B7 00 07 add [edi], al
000003B9 00 00 add [eax], al
000003BB 00 02 add [edx], al
000003BD 00 00 add [eax], al
000003BF 00 00 add [eax], al
000003C1 00 00 add [eax], al
000003C3 00 00 add [eax], al
000003C5 00 00 add [eax], al
000003C7 00 48 83 add [eax-0x7D], cl
000003CA EC in al, dx
000003CB 08 E8 or al, ch
000003CD 6B 00 00 imul eax, [eax], 0x00
000003D0 00 E8 add al, ch
000003D2 FA cli
000003D3 00 00 add [eax], al
000003D5 00 E8 add al, ch
000003D7 D5 01 aad 0x01
000003D9 00 00 add [eax], al
000003DB 48 dec eax
000003DC 83 C4 08 add esp, 0x08
000003DF C3 ret
00000343 5F pop edi
00000344 6D ins es:[edi], edx
00000345 61 popa
00000346 69 6E 00 47 4C 49 42 imul ebp, [esi+], 0x42494C47
0000034D 43 inc ebx
0000034E 5F pop edi
0000034F 32 2E xor ch, [esi]
00000351 32 2E xor ch, [esi]
00000353 35 00 00 00 00 xor eax, 0x00000000
00000358 02 00 add al, [eax]
0000035A 02 00 add al, [eax]
0000035C 00 00 add [eax], al
0000035E 00 00 add [eax], al
00000360 01 00 add [eax], eax
00000362 01 00 add [eax], eax
00000364 10 00 adc [eax], al
00000366 00 00 add [eax], al
00000368 10 00 adc [eax], al
0000036A 00 00 add [eax], al
0000036C 00 00 add [eax], al
0000036E 00 00 add [eax], al
00000370 75 1A jnz 0x0000038C
0000038C 03 00 add eax, [eax]
0000038E 00 00 add [eax], al
00000390 00 00 add [eax], al
00000392 00 00 add [eax], al
00000394 00 00 add [eax], al
00000396 00 00 add [eax], al
00000398 00 10 add [eax], dl
0000039A 60 pusha
0000039B 00 00 add [eax], al
0000039D 00 00 add [eax], al
0000039F 00 07 add [edi], al
000003A1 00 00 add [eax], al
000003A3 00 01 add [ecx], al
000003A5 00 00 add [eax], al
000003A7 00 00 add [eax], al
000003A9 00 00 add [eax], al
000003AB 00 00 add [eax], al
000003AD 00 00 add [eax], al
000003AF 00 08 add [eax], cl
000003B1 10 60 00 adc [eax+], ah
000003B4 00 00 add [eax], al
000003B6 00 00 add [eax], al
000003B8 07 pop es
000003B9 00 00 add [eax], al
000003BB 00 02 add [edx], al
000003BD 00 00 add [eax], al
000003BF 00 00 add [eax], al
000003C1 00 00 add [eax], al
000003C3 00 00 add [eax], al
000003C5 00 00 add [eax], al
000003C7 00 48 83 add [eax-0x7D], cl
000003CA EC in al, dx
000003CB 08 E8 or al, ch
000003CD 6B 00 00 imul eax, [eax], 0x00
000003D0 00 E8 add al, ch
000003D2 FA cli
000003D3 00 00 add [eax], al
000003D5 00 E8 add al, ch
000003D7 D5 01 aad 0x01
000003D9 00 00 add [eax], al
000003DB 48 dec eax
000003DC 83 C4 08 add esp, 0x08
000003DF C3 ret
00000372 69 09 00 00 02 00 imul ecx, [ecx], 0x00020000
00000378 31 00 xor [eax], eax
0000037A 00 00 add [eax], al
0000037C 00 00 add [eax], al
0000037E 00 00 add [eax], al
00000380 E0 0F loopnz 0x00000391
00000391 00 00 add [eax], al
00000393 00 00 add [eax], al
00000395 00 00 add [eax], al
00000397 00 00 add [eax], al
00000399 10 60 00 adc [eax+], ah
0000039C 00 00 add [eax], al
0000039E 00 00 add [eax], al
000003A0 07 pop es
000003A1 00 00 add [eax], al
000003A3 00 01 add [ecx], al
000003A5 00 00 add [eax], al
000003A7 00 00 add [eax], al
000003A9 00 00 add [eax], al
000003AB 00 00 add [eax], al
000003AD 00 00 add [eax], al
000003AF 00 08 add [eax], cl
000003B1 10 60 00 adc [eax+], ah
000003B4 00 00 add [eax], al
000003B6 00 00 add [eax], al
000003B8 07 pop es
000003B9 00 00 add [eax], al
000003BB 00 02 add [edx], al
000003BD 00 00 add [eax], al
000003BF 00 00 add [eax], al
000003C1 00 00 add [eax], al
000003C3 00 00 add [eax], al
000003C5 00 00 add [eax], al
000003C7 00 48 83 add [eax-0x7D], cl
000003CA EC in al, dx
000003CB 08 E8 or al, ch
000003CD 6B 00 00 imul eax, [eax], 0x00
000003D0 00 E8 add al, ch
000003D2 FA cli
000003D3 00 00 add [eax], al
000003D5 00 E8 add al, ch
000003D7 D5 01 aad 0x01
000003D9 00 00 add [eax], al
000003DB 48 dec eax
000003DC 83 C4 08 add esp, 0x08
000003DF C3 ret
00000382 60 pusha
00000383 00 00 add [eax], al
00000385 00 00 add [eax], al
00000387 00 06 add [esi], al
00000389 00 00 add [eax], al
0000038B 00 03 add [ebx], al
0000038D 00 00 add [eax], al
0000038F 00 00 add [eax], al
00000391 00 00 add [eax], al
00000393 00 00 add [eax], al
00000395 00 00 add [eax], al
00000397 00 00 add [eax], al
00000399 10 60 00 adc [eax+], ah
0000039C 00 00 add [eax], al
0000039E 00 00 add [eax], al
000003A0 07 pop es
000003A1 00 00 add [eax], al
000003A3 00 01 add [ecx], al
000003A5 00 00 add [eax], al
000003A7 00 00 add [eax], al
000003A9 00 00 add [eax], al
000003AB 00 00 add [eax], al
000003AD 00 00 add [eax], al
000003AF 00 08 add [eax], cl
000003B1 10 60 00 adc [eax+], ah
000003B4 00 00 add [eax], al
000003B6 00 00 add [eax], al
000003B8 07 pop es
000003B9 00 00 add [eax], al
000003BB 00 02 add [edx], al
000003BD 00 00 add [eax], al
000003BF 00 00 add [eax], al
000003C1 00 00 add [eax], al
000003C3 00 00 add [eax], al
000003C5 00 00 add [eax], al
000003C7 00 48 83 add [eax-0x7D], cl
000003CA EC in al, dx
000003CB 08 E8 or al, ch
000003CD 6B 00 00 imul eax, [eax], 0x00
000003D0 00 E8 add al, ch
000003D2 FA cli
000003D3 00 00 add [eax], al
000003D5 00 E8 add al, ch
000003D7 D5 01 aad 0x01
000003D9 00 00 add [eax], al
000003DB 48 dec eax
000003DC 83 C4 08 add esp, 0x08
000003DF C3 ret
00000204 04 00 add al, 0x00
00000206 00 00 add [eax], al
00000208 28 0E sub [esi], cl
0000020A 00 00 add [eax], al
0000020C 00 00 add [eax], al
0000020E 00 00 add [eax], al
00000210 28 0E sub [esi], cl
00000212 60 pusha
00000213 00 00 add [eax], al
00000215 00 00 add [eax], al
00000217 00 28 add [eax], ch
00000219 0E push cs
0000021A 60 pusha
0000021B 00 00 add [eax], al
0000021D 00 00 add [eax], al
0000021F 00 D8 add al, bl
00000221 01 00 add [eax], eax
00000223 00 00 add [eax], al
00000225 00 00 add [eax], al
00000227 00 D8 add al, bl
00000229 01 00 add [eax], eax
0000022B 00 00 add [eax], al
0000022D 00 00 add [eax], al
0000022F 00 01 add [ecx], al
00000231 00 00 add [eax], al
00000233 00 00 add [eax], al
00000235 00 00 add [eax], al
00000237 00 2F add [edi], ch
00000239 6C ins es:[edi], dl
0000023A 69 62 36 34 2F 6C 64 imul esp, [edx+0x36], 0x646C2F34
00000241 2D 6C 69 6E 75 sub eax, 0x756E696C
00000246 78 2D js 0x00000275
00000275 00 00 add [eax], al
00000277 00 14 00 add [eax+eax], dl
0000027A 00 00 add [eax], al
0000027C 03 00 add eax, [eax]
0000027E 00 00 add [eax], al
00000280 47 inc edi
00000281 4E dec esi
00000282 55 push ebp
00000283 00 B3 7B 8F 7D 1D add [ebx+0x1D7D8F7B], dh
00000289 1F pop ds
0000028A 19 A7 98 A2 38 EA sbb [edi-0x15C75D68], esp
00000290 D3 F7 sal edi, cl
00000292 97 xchg eax, edi
00000293 9C pushf
00000294 12 ED adc ch, ch
00000296 41 inc ecx
00000297 D1 01 rol [ecx], 0x00000001
00000299 00 00 add [eax], al
0000029B 00 01 add [ecx], al
0000029D 00 00 add [eax], al
0000029F 00 01 add [ecx], al
000002A1 00 00 add [eax], al
000002A3 00 00 add [eax], al
000002A5 00 00 add [eax], al
000002A7 00 00 add [eax], al
000002A9 00 00 add [eax], al
000002AB 00 00 add [eax], al
000002AD 00 00 add [eax], al
000002AF 00 00 add [eax], al
000002B1 00 00 add [eax], al
000002B3 00 00 add [eax], al
000002B5 00 00 add [eax], al
000002B7 00 00 add [eax], al
000002B9 00 00 add [eax], al
000002BB 00 00 add [eax], al
000002BD 00 00 add [eax], al
000002BF 00 00 add [eax], al
000002C1 00 00 add [eax], al
000002C3 00 00 add [eax], al
000002C5 00 00 add [eax], al
000002C7 00 00 add [eax], al
000002C9 00 00 add [eax], al
000002CB 00 00 add [eax], al
000002CD 00 00 add [eax], al
000002CF 00 1A add [edx], bl
000002D1 00 00 add [eax], al
000002D3 00 12 add [edx], dl
000002D5 00 00 add [eax], al
000002D7 00 00 add [eax], al
000002D9 00 00 add [eax], al
000002DB 00 00 add [eax], al
000002DD 00 00 add [eax], al
000002DF 00 00 add [eax], al
000002E1 00 00 add [eax], al
000002E3 00 00 add [eax], al
000002E5 00 00 add [eax], al
000002E7 00 1F add [edi], bl
000002E9 00 00 add [eax], al
000002EB 00 12 add [edx], dl
000002ED 00 00 add [eax], al
000002EF 00 00 add [eax], al
000002F1 00 00 add [eax], al
000002F3 00 00 add [eax], al
000002F5 00 00 add [eax], al
000002F7 00 00 add [eax], al
000002F9 00 00 add [eax], al
000002FB 00 00 add [eax], al
000002FD 00 00 add [eax], al
000002FF 00 01 add [ecx], al
00000301 00 00 add [eax], al
00000303 00 20 add [eax], ah
00000305 00 00 add [eax], al
00000307 00 00 add [eax], al
00000309 00 00 add [eax], al
0000030B 00 00 add [eax], al
0000030D 00 00 add [eax], al
0000030F 00 00 add [eax], al
00000311 00 00 add [eax], al
00000313 00 00 add [eax], al
00000315 00 00 add [eax], al
00000317 00 00 add [eax], al
00000319 5F pop edi
0000031A 5F pop edi
0000031B 67 6D ins es:[edi], edx
0000031D 6F outs edx, ds:[esi]
0000031E 6E outs dl, ds:[esi]
0000031F 5F pop edi
00000320 73 74 jnc 0x00000396
00000322 61 popa
00000323 72 74 jc 0x00000399
00000325 5F pop edi
00000326 5F pop edi
00000327 00 6C 69 62 add [ecx+ebp*2+0x62], ch
0000032B 63 2E arpl [esi], bp
0000032D 73 6F jnc 0x0000039E
0000032F 2E 36 00 70 75 add ds:[eax+0x75], dh
00000334 74 73 jz 0x000003A9
00000336 00 5F 5F add [edi+0x5F], bl
00000339 6C ins es:[edi], dl
0000033A 69 62 63 5F 73 74 61 imul esp, [edx+0x63], 0x6174735F
00000341 72 74 jc 0x000003B7
00000343 5F pop edi
00000344 6D ins es:[edi], edx
00000345 61 popa
00000346 69 6E 00 47 4C 49 42 imul ebp, [esi+], 0x42494C47
0000034D 43 inc ebx
0000034E 5F pop edi
0000034F 32 2E xor ch, [esi]
00000351 32 2E xor ch, [esi]
00000353 35 00 00 00 00 xor eax, 0x00000000
00000358 02 00 add al, [eax]
0000035A 02 00 add al, [eax]
0000035C 00 00 add [eax], al
0000035E 00 00 add [eax], al
00000360 01 00 add [eax], eax
00000362 01 00 add [eax], eax
00000364 10 00 adc [eax], al
00000366 00 00 add [eax], al
00000368 10 00 adc [eax], al
0000036A 00 00 add [eax], al
0000036C 00 00 add [eax], al
0000036E 00 00 add [eax], al
00000370 75 1A jnz 0x0000038C
00000372 69 09 00 00 02 00 imul ecx, [ecx], 0x00020000
00000378 31 00 xor [eax], eax
0000037A 00 00 add [eax], al
0000037C 00 00 add [eax], al
0000037E 00 00 add [eax], al
00000380 E0 0F loopnz 0x00000391
00000382 60 pusha
00000383 00 00 add [eax], al
00000385 00 00 add [eax], al
00000387 00 06 add [esi], al
00000389 00 00 add [eax], al
0000038B 00 03 add [ebx], al
0000038D 00 00 add [eax], al
0000038F 00 00 add [eax], al
00000391 00 00 add [eax], al
00000393 00 00 add [eax], al
00000395 00 00 add [eax], al
00000397 00 00 add [eax], al
00000399 10 60 00 adc [eax+], ah
0000039C 00 00 add [eax], al
0000039E 00 00 add [eax], al
000003A0 07 pop es
000003A1 00 00 add [eax], al
000003A3 00 01 add [ecx], al
000003A5 00 00 add [eax], al
000003A7 00 00 add [eax], al
000003A9 00 00 add [eax], al
000003AB 00 00 add [eax], al
000003AD 00 00 add [eax], al
000003AF 00 08 add [eax], cl
000003B1 10 60 00 adc [eax+], ah
000003B4 00 00 add [eax], al
000003B6 00 00 add [eax], al
000003B8 07 pop es
000003B9 00 00 add [eax], al
000003BB 00 02 add [edx], al
000003BD 00 00 add [eax], al
000003BF 00 00 add [eax], al
000003C1 00 00 add [eax], al
000003C3 00 00 add [eax], al
000003C5 00 00 add [eax], al
000003C7 00 48 83 add [eax-0x7D], cl
000003CA EC in al, dx
000003CB 08 E8 or al, ch
000003CD 6B 00 00 imul eax, [eax], 0x00
000003D0 00 E8 add al, ch
000003D2 FA cli
000003D3 00 00 add [eax], al
000003D5 00 E8 add al, ch
000003D7 D5 01 aad 0x01
000003D9 00 00 add [eax], al
000003DB 48 dec eax
000003DC 83 C4 08 add esp, 0x08
000003DF C3 ret
00000248 78 38 js 0x00000282
00000282 55 push ebp
00000283 00 B3 7B 8F 7D 1D add [ebx+0x1D7D8F7B], dh
00000289 1F pop ds
0000028A 19 A7 98 A2 38 EA sbb [edi-0x15C75D68], esp
00000290 D3 F7 sal edi, cl
00000292 97 xchg eax, edi
00000293 9C pushf
00000294 12 ED adc ch, ch
00000296 41 inc ecx
00000297 D1 01 rol [ecx], 0x00000001
00000299 00 00 add [eax], al
0000029B 00 01 add [ecx], al
0000029D 00 00 add [eax], al
0000029F 00 01 add [ecx], al
000002A1 00 00 add [eax], al
000002A3 00 00 add [eax], al
000002A5 00 00 add [eax], al
000002A7 00 00 add [eax], al
000002A9 00 00 add [eax], al
000002AB 00 00 add [eax], al
000002AD 00 00 add [eax], al
000002AF 00 00 add [eax], al
000002B1 00 00 add [eax], al
000002B3 00 00 add [eax], al
000002B5 00 00 add [eax], al
000002B7 00 00 add [eax], al
000002B9 00 00 add [eax], al
000002BB 00 00 add [eax], al
000002BD 00 00 add [eax], al
000002BF 00 00 add [eax], al
000002C1 00 00 add [eax], al
000002C3 00 00 add [eax], al
000002C5 00 00 add [eax], al
000002C7 00 00 add [eax], al
000002C9 00 00 add [eax], al
000002CB 00 00 add [eax], al
000002CD 00 00 add [eax], al
000002CF 00 1A add [edx], bl
000002D1 00 00 add [eax], al
000002D3 00 12 add [edx], dl
000002D5 00 00 add [eax], al
000002D7 00 00 add [eax], al
000002D9 00 00 add [eax], al
000002DB 00 00 add [eax], al
000002DD 00 00 add [eax], al
000002DF 00 00 add [eax], al
000002E1 00 00 add [eax], al
000002E3 00 00 add [eax], al
000002E5 00 00 add [eax], al
000002E7 00 1F add [edi], bl
000002E9 00 00 add [eax], al
000002EB 00 12 add [edx], dl
000002ED 00 00 add [eax], al
000002EF 00 00 add [eax], al
000002F1 00 00 add [eax], al
000002F3 00 00 add [eax], al
000002F5 00 00 add [eax], al
000002F7 00 00 add [eax], al
000002F9 00 00 add [eax], al
000002FB 00 00 add [eax], al
000002FD 00 00 add [eax], al
000002FF 00 01 add [ecx], al
00000301 00 00 add [eax], al
00000303 00 20 add [eax], ah
00000305 00 00 add [eax], al
00000307 00 00 add [eax], al
00000309 00 00 add [eax], al
0000030B 00 00 add [eax], al
0000030D 00 00 add [eax], al
0000030F 00 00 add [eax], al
00000311 00 00 add [eax], al
00000313 00 00 add [eax], al
00000315 00 00 add [eax], al
00000317 00 00 add [eax], al
00000319 5F pop edi
0000031A 5F pop edi
0000031B 67 6D ins es:[edi], edx
0000031D 6F outs edx, ds:[esi]
0000031E 6E outs dl, ds:[esi]
0000031F 5F pop edi
00000320 73 74 jnc 0x00000396
00000322 61 popa
00000323 72 74 jc 0x00000399
00000325 5F pop edi
00000326 5F pop edi
00000327 00 6C 69 62 add [ecx+ebp*2+0x62], ch
0000032B 63 2E arpl [esi], bp
0000032D 73 6F jnc 0x0000039E
0000032F 2E 36 00 70 75 add ds:[eax+0x75], dh
00000334 74 73 jz 0x000003A9
00000336 00 5F 5F add [edi+0x5F], bl
00000339 6C ins es:[edi], dl
0000033A 69 62 63 5F 73 74 61 imul esp, [edx+0x63], 0x6174735F
00000341 72 74 jc 0x000003B7
00000343 5F pop edi
00000344 6D ins es:[edi], edx
00000345 61 popa
00000346 69 6E 00 47 4C 49 42 imul ebp, [esi+], 0x42494C47
0000034D 43 inc ebx
0000034E 5F pop edi
0000034F 32 2E xor ch, [esi]
00000351 32 2E xor ch, [esi]
00000353 35 00 00 00 00 xor eax, 0x00000000
00000358 02 00 add al, [eax]
0000035A 02 00 add al, [eax]
0000035C 00 00 add [eax], al
0000035E 00 00 add [eax], al
00000360 01 00 add [eax], eax
00000362 01 00 add [eax], eax
00000364 10 00 adc [eax], al
00000366 00 00 add [eax], al
00000368 10 00 adc [eax], al
0000036A 00 00 add [eax], al
0000036C 00 00 add [eax], al
0000036E 00 00 add [eax], al
00000370 75 1A jnz 0x0000038C
00000372 69 09 00 00 02 00 imul ecx, [ecx], 0x00020000
00000378 31 00 xor [eax], eax
0000037A 00 00 add [eax], al
0000037C 00 00 add [eax], al
0000037E 00 00 add [eax], al
00000380 E0 0F loopnz 0x00000391
00000382 60 pusha
00000383 00 00 add [eax], al
00000385 00 00 add [eax], al
00000387 00 06 add [esi], al
00000389 00 00 add [eax], al
0000038B 00 03 add [ebx], al
0000038D 00 00 add [eax], al
0000038F 00 00 add [eax], al
00000391 00 00 add [eax], al
00000393 00 00 add [eax], al
00000395 00 00 add [eax], al
00000397 00 00 add [eax], al
00000399 10 60 00 adc [eax+], ah
0000039C 00 00 add [eax], al
0000039E 00 00 add [eax], al
000003A0 07 pop es
000003A1 00 00 add [eax], al
000003A3 00 01 add [ecx], al
000003A5 00 00 add [eax], al
000003A7 00 00 add [eax], al
000003A9 00 00 add [eax], al
000003AB 00 00 add [eax], al
000003AD 00 00 add [eax], al
000003AF 00 08 add [eax], cl
000003B1 10 60 00 adc [eax+], ah
000003B4 00 00 add [eax], al
000003B6 00 00 add [eax], al
000003B8 07 pop es
000003B9 00 00 add [eax], al
000003BB 00 02 add [edx], al
000003BD 00 00 add [eax], al
000003BF 00 00 add [eax], al
000003C1 00 00 add [eax], al
000003C3 00 00 add [eax], al
000003C5 00 00 add [eax], al
000003C7 00 48 83 add [eax-0x7D], cl
000003CA EC in al, dx
000003CB 08 E8 or al, ch
000003CD 6B 00 00 imul eax, [eax], 0x00
000003D0 00 E8 add al, ch
000003D2 FA cli
000003D3 00 00 add [eax], al
000003D5 00 E8 add al, ch
000003D7 D5 01 aad 0x01
000003D9 00 00 add [eax], al
000003DB 48 dec eax
000003DC 83 C4 08 add esp, 0x08
000003DF C3 ret
0000024A 36 2D 36 34 2E 73 sub eax, 0x732E3436
00000250 6F outs edx, ds:[esi]
00000251 2E 32 00 xor al, cs:[eax]
00000254 04 00 add al, 0x00
00000256 00 00 add [eax], al
00000258 10 00 adc [eax], al
0000025A 00 00 add [eax], al
0000025C 01 00 add [eax], eax
0000025E 00 00 add [eax], al
00000260 47 inc edi
00000261 4E dec esi
00000262 55 push ebp
00000263 00 00 add [eax], al
00000265 00 00 add [eax], al
00000267 00 02 add [edx], al
00000269 00 00 add [eax], al
0000026B 00 06 add [esi], al
0000026D 00 00 add [eax], al
0000026F 00 18 add [eax], bl
00000271 00 00 add [eax], al
00000273 00 04 00 add [eax+eax], al
00000276 00 00 add [eax], al
00000278 14 00 adc al, 0x00
0000027A 00 00 add [eax], al
0000027C 03 00 add eax, [eax]
0000027E 00 00 add [eax], al
00000280 47 inc edi
00000281 4E dec esi
00000282 55 push ebp
00000283 00 B3 7B 8F 7D 1D add [ebx+0x1D7D8F7B], dh
00000289 1F pop ds
0000028A 19 A7 98 A2 38 EA sbb [edi-0x15C75D68], esp
00000290 D3 F7 sal edi, cl
00000292 97 xchg eax, edi
00000293 9C pushf
00000294 12 ED adc ch, ch
00000296 41 inc ecx
00000297 D1 01 rol [ecx], 0x00000001
00000299 00 00 add [eax], al
0000029B 00 01 add [ecx], al
0000029D 00 00 add [eax], al
0000029F 00 01 add [ecx], al
000002A1 00 00 add [eax], al
000002A3 00 00 add [eax], al
000002A5 00 00 add [eax], al
000002A7 00 00 add [eax], al
000002A9 00 00 add [eax], al
000002AB 00 00 add [eax], al
000002AD 00 00 add [eax], al
000002AF 00 00 add [eax], al
000002B1 00 00 add [eax], al
000002B3 00 00 add [eax], al
000002B5 00 00 add [eax], al
000002B7 00 00 add [eax], al
000002B9 00 00 add [eax], al
000002BB 00 00 add [eax], al
000002BD 00 00 add [eax], al
000002BF 00 00 add [eax], al
000002C1 00 00 add [eax], al
000002C3 00 00 add [eax], al
000002C5 00 00 add [eax], al
000002C7 00 00 add [eax], al
000002C9 00 00 add [eax], al
000002CB 00 00 add [eax], al
000002CD 00 00 add [eax], al
000002CF 00 1A add [edx], bl
000002D1 00 00 add [eax], al
000002D3 00 12 add [edx], dl
000002D5 00 00 add [eax], al
000002D7 00 00 add [eax], al
000002D9 00 00 add [eax], al
000002DB 00 00 add [eax], al
000002DD 00 00 add [eax], al
000002DF 00 00 add [eax], al
000002E1 00 00 add [eax], al
000002E3 00 00 add [eax], al
000002E5 00 00 add [eax], al
000002E7 00 1F add [edi], bl
000002E9 00 00 add [eax], al
000002EB 00 12 add [edx], dl
000002ED 00 00 add [eax], al
000002EF 00 00 add [eax], al
000002F1 00 00 add [eax], al
000002F3 00 00 add [eax], al
000002F5 00 00 add [eax], al
000002F7 00 00 add [eax], al
000002F9 00 00 add [eax], al
000002FB 00 00 add [eax], al
000002FD 00 00 add [eax], al
000002FF 00 01 add [ecx], al
00000301 00 00 add [eax], al
00000303 00 20 add [eax], ah
00000305 00 00 add [eax], al
00000307 00 00 add [eax], al
00000309 00 00 add [eax], al
0000030B 00 00 add [eax], al
0000030D 00 00 add [eax], al
0000030F 00 00 add [eax], al
00000311 00 00 add [eax], al
00000313 00 00 add [eax], al
00000315 00 00 add [eax], al
00000317 00 00 add [eax], al
00000319 5F pop edi
0000031A 5F pop edi
0000031B 67 6D ins es:[edi], edx
0000031D 6F outs edx, ds:[esi]
0000031E 6E outs dl, ds:[esi]
0000031F 5F pop edi
00000320 73 74 jnc 0x00000396
00000322 61 popa
00000323 72 74 jc 0x00000399
00000325 5F pop edi
00000326 5F pop edi
00000327 00 6C 69 62 add [ecx+ebp*2+0x62], ch
0000032B 63 2E arpl [esi], bp
0000032D 73 6F jnc 0x0000039E
0000032F 2E 36 00 70 75 add ds:[eax+0x75], dh
00000334 74 73 jz 0x000003A9
00000336 00 5F 5F add [edi+0x5F], bl
00000339 6C ins es:[edi], dl
0000033A 69 62 63 5F 73 74 61 imul esp, [edx+0x63], 0x6174735F
00000341 72 74 jc 0x000003B7
00000343 5F pop edi
00000344 6D ins es:[edi], edx
00000345 61 popa
00000346 69 6E 00 47 4C 49 42 imul ebp, [esi+], 0x42494C47
0000034D 43 inc ebx
0000034E 5F pop edi
0000034F 32 2E xor ch, [esi]
00000351 32 2E xor ch, [esi]
00000353 35 00 00 00 00 xor eax, 0x00000000
00000358 02 00 add al, [eax]
0000035A 02 00 add al, [eax]
0000035C 00 00 add [eax], al
0000035E 00 00 add [eax], al
00000360 01 00 add [eax], eax
00000362 01 00 add [eax], eax
00000364 10 00 adc [eax], al
00000366 00 00 add [eax], al
00000368 10 00 adc [eax], al
0000036A 00 00 add [eax], al
0000036C 00 00 add [eax], al
0000036E 00 00 add [eax], al
00000370 75 1A jnz 0x0000038C
00000372 69 09 00 00 02 00 imul ecx, [ecx], 0x00020000
00000378 31 00 xor [eax], eax
0000037A 00 00 add [eax], al
0000037C 00 00 add [eax], al
0000037E 00 00 add [eax], al
00000380 E0 0F loopnz 0x00000391
00000382 60 pusha
00000383 00 00 add [eax], al
00000385 00 00 add [eax], al
00000387 00 06 add [esi], al
00000389 00 00 add [eax], al
0000038B 00 03 add [ebx], al
0000038D 00 00 add [eax], al
0000038F 00 00 add [eax], al
00000391 00 00 add [eax], al
00000393 00 00 add [eax], al
00000395 00 00 add [eax], al
00000397 00 00 add [eax], al
00000399 10 60 00 adc [eax+], ah
0000039C 00 00 add [eax], al
0000039E 00 00 add [eax], al
000003A0 07 pop es
000003A1 00 00 add [eax], al
000003A3 00 01 add [ecx], al
000003A5 00 00 add [eax], al
000003A7 00 00 add [eax], al
000003A9 00 00 add [eax], al
000003AB 00 00 add [eax], al
000003AD 00 00 add [eax], al
000003AF 00 08 add [eax], cl
000003B1 10 60 00 adc [eax+], ah
000003B4 00 00 add [eax], al
000003B6 00 00 add [eax], al
000003B8 07 pop es
000003B9 00 00 add [eax], al
000003BB 00 02 add [edx], al
000003BD 00 00 add [eax], al
000003BF 00 00 add [eax], al
000003C1 00 00 add [eax], al
000003C3 00 00 add [eax], al
000003C5 00 00 add [eax], al
000003C7 00 48 83 add [eax-0x7D], cl
000003CA EC in al, dx
000003CB 08 E8 or al, ch
000003CD 6B 00 00 imul eax, [eax], 0x00
000003D0 00 E8 add al, ch
000003D2 FA cli
000003D3 00 00 add [eax], al
000003D5 00 E8 add al, ch
000003D7 D5 01 aad 0x01
000003D9 00 00 add [eax], al
000003DB 48 dec eax
000003DC 83 C4 08 add esp, 0x08
000003DF C3 ret

```
