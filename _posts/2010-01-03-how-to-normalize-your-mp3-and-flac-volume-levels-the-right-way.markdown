---
layout: post
published: true
title: How to normalize your MP3 and Flac volume levels (the right way)
permalink: /how-to-normalize-your-mp3-and-flac-volume-levels-the-right-way/
wordpress_id: 891
categories:
- News
- mp3
- howto
- songs
- volume
- album
- gain
- analysis
- how to
- mp3 gain
- mp3 volume
- Mp3Gain
- Mp3Volume
- normalize
- normalize volume
- NormalizeVolume
- volume leveller
- VolumeLeveller
- audio software
- David Robinson
- Replay Gain algorithm
- normalize flac
---


Most audio software these days offer either built-in or plug-in functionality that will attempt to level the volume of your MP3 files so that you aren't turning the volume up to hear soft songs, then getting blasted by louder ones. So why is it that even after turning that option on, you sometimes notice a significant volume difference between some songs? What's worse is when you're listening to songs from the same album, and the volumes jump around abnormally after applying volume normalization.

The problem is that the vast majority of audio player programs use peak amplitude analysis to determine how "loud" a song is and normalize based on that, rather than doing a more comprehensive analysis of the frequencies that impact how loud the music actually sounds. But even those that do a more comprehensive analysis fail to consider songs within the context of the album they belong to.

Luckily, there's a great little utility called <a href="http://mp3gain.sourceforge.net/">MP3 Gain</a> that does lossless volume analysis and adjustment based on David Robinson's <a href="http://wiki.hydrogenaudio.org/index.php?title=ReplayGain_specification">Replay Gain algorithm</a>, as well as allowing for the volume of entire albums to be processed. Radio analysis and gain adjustment will adjust all songs to the same maximum decibel level. Album mode analyzes all of the songs in an album, essentially considering them to be one entire song, then adjusts them all to a maximum decibel level, but maintains their relative volume.


