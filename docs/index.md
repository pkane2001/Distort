---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
sidebar: mydoc_sidebar
layout: "page"
toc: false
title: Distort audibility tester
comments: true
---

![distort](images/distort1.png)

## What do I need to run Distort?
DeltaWave runs on Microsoft Windows and required .NET 4.6 framework to be installed.
The software is very CPU and memory intensive, recommended configuration at least an I7 4-core processor and 8GB or more of RAM.


## How do I get it?
Here you go:
<a href="DistortSetup.zip">Download v1.0.8 64-bit <input type="image" id="download" alt="Download" src="images/windows-logo.png" width="30" align="top" />   </a>


Please check this website to get an updated copy!

Once the file downloads, extract the installer from ZIP archive and run it to install. Follow prompts.


## How do I use it?

Run Distort, pick a WAV file you may want to apply distortion to by clicking on the File: button. 

* Move the sliders on the right up and down to adjust the harmonic level. The first slider (on the left) adjusts the shape of the decreasing amplitude of harmonics. The right slider adjusts the overall amplitude of all the harmonics. Once adjustment is made, it could take a few moments for the charts to refresh.

* You can turn off all odd or all even harmonics by unchecking the appropriate checkbox. Alternatively, you can set the adjustment level to adjust the amplitude of just the odd or just the even harmonics. These settings apply on top of the setting selected using the two sliders.

* If you want to make direct adjustments to harmonics levels, click on the Custom... checkbox and enter the desired dB level for each of the harmonics. When Custom is checked, the settings selected using sliders and odd/even checks are ignored.

![Custom](images/distort2.png)

* You can also set the desired noise floor. Click on Noise... checkbox to select it. Enter the desired noise floor shape (white or pink) and the desired level in dB. Press Apply to see the changes reflected on the plots. You can also add a 50Hz or 60Hz mains frequency spike at the desired level. Noise floor settings apply in addition to all other harmonics settings.

![Noise](images/distort3.png)

* When the desired look and level of THD, THD+N and harmonics is achieved, you can press the Play button to hear the distorted file you picked through the audio system connected to your PC, or you can click Save to write the file out to disk, with all the distortions already applied.

* If desired, you can also pick a low pass filter frequency. This is to eliminate the effect of harmonic distortion beyond audible frequencies, say above 20kHz. This filter is applied only when saving a file, not when playing it.

## What's new in...

### v1.0.8
* Fix for 50Hz/60Hz/12000Hz test signals not working

### v1.0.7
* Added support for DirectSound playback (any \[DS\] drivers in the driver list)
* Added input validation on Noise Settings form
* Changed default values for both, Noise Settings and Custom Harmonics to -300dB from 0

### v1.0.6
* Added additional single and dual tone display options
* Fixed reported error when no audio driver is selected
* Fixed reported issue when an audio driver claims to support more bits than it can handle
* Save... dialog now remembers previous directory

### v1.0.5
* Added ability to save and reload distortion settings from a file
* Added brown noise floor option (-6dB/octave)


___
{% include links.html %}
