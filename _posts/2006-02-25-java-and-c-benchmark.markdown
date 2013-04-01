---
layout: post
published: true
title: Java and  C benchmark
permalink: /java-and-c-benchmark/
wordpress_id: 184
categories:
- News
- Linux
- Java
- C++
---
<strong>C benchmark</strong>

```

node1:~/src/benchmark# wget http://www.ocf.berkeley.edu/~cowell/research/benchmark/code/Benchmark.c
node1:~/src/benchmark# gcc -lm -o Benchmark Benchmark.c
node1:~/src/benchmark# ./Benchmark
Start C benchmark
Int arithmetic elapsed time: 15490 ms with intMax of 1000000000
 i: 1000000001
 intResult: 1
Double arithmetic elapsed time: 14200 ms with doubleMin 10000000000.000000, doubleMax 11000000000.000000
 i: 11000000000.000000
 doubleResult: 10011632717.505636
Long arithmetic elapsed time: 25540 ms with longMin                                                       1410065408, longMax                                                                2
 i:                                                      -1884901888
 longResult:                                                        776627965
Trig elapsed time: 3420 ms with max of 10000000
 i: 10000000.000000
 sine: 0.990665
 cosine: -0.136322
 tangent: -7.267119
 logarithm: 7.000000
 squareRoot: 3162.277502
I/O elapsed time: 720 ms with max of 1000000
 last line: abcdefghijklmnopqrstuvwxyz1234567890abcdefghijklmnopqrstuvwxyz1234567890abcdefgh
Total elapsed time: 59370 ms
Stop C benchmark

```


<strong>Java  benchmark</strong>

```

node1:~/src/benchmark# wget http://www.ocf.berkeley.edu/~cowell/research/benchmark/code/Benchmark.java
node1:~/src/benchmark# javac Benchmark.java
node1:~/src/benchmark# java Benchmark
Start Java benchmark
Int arithmetic elapsed time: 10875 ms with max of 1000000000
 i: 1000000001
 intResult: 1
Double arithmetic elapsed time: 13159 ms with min of 1.0E10, max of 1.1E10
 i: 1.1E10
 doubleResult: 1.00116327174955E10
Long arithmetic elapsed time: 30829 ms with min of 10000000000, max of 11000000000
 i: 11000000000
 longResult: 776627965
Trig elapsed time: 49449 ms with max of 1.0E7
 i: 1.0E7
 sine: 0.9906646477361263
 cosine: -0.13632151600483616
 tangent: -7.267118770165242
 logarithm: 16.118095550958316
 squareRoot: 3162.2775020544923
IO elapsed time: 2525 ms with max of 1000000
 i: 1000001
 myLine: abcdefghijklmnopqrstuvwxyz1234567890abcdefghijklmnopqrstuvwxyz1234567890abcdefgh
Total Java benchmark time: 106837 ms
End Java benchmark

```


