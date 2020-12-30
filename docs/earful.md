---
title: Earful - Audiophile Hearing Test App
tags: [Earful]
keywords: release notes, announcements, what's new, new features
last_updated: Dec 27, 2020
summary: "Earful v1.0 is the initial beta release of this software. Use at your own risk!"
sidebar: mydoc_sidebar
permalink: earful.html
folder: mydoc
toc: false
comments: true
---

![distort](images/earful1.png)


<br>
<br>


<a href="EarfulSetup.zip">Download Earful for Windows v1.0.11   <input type="image" id="ear" alt="Earful" src="images/earful_logo.png" width="30" align="top" />   </a>



## You may also be interested in these:
* <a href="https://deltaw.org" target="_blank">DeltaWave</a> - Audio null analyzer and audibility tester
* <a href="https://distortaudio.org" target="_blank">DISTORT</a> - Your personal simulation of what various distortions do to audio
<br>


## What is it? And a WARNING!
Earful is an app designed to measure and evaluate the lower threshold of hearing across a frequency spectrum. It is designed to run on Windows and support ASIO, WASAPI, and Direct Sound audio devices. Use with headphones is recommended for greater accuracy and noise elimination.

In addition, with version .10, Earful now supports two other types of tests: 
* Equal-loudness testing using the same device and 1kHz reference tone
* Two devices equal-loudness testing, using a reference device, such as speakers, and a test devices, such as headphones

The app is free to use, but to use it, you must agree to do so *AT YOUR OWN RISK ONLY*. Make sure that the volume settings are set such that any loud sounds played through your system will not damage your equipment or your hearing! This is important. Set the frequency range in Earful correctly, and also specify the maximum volume setting at a low number to avoid surprises (default is -20dBFS).

## Features
* Pick your own frequency range for the test
* Specify any number of logarithmically spread points to test along the frequency axis
* Compare your results to others, compare to your older tests to check for changes, or compare to any of the industry standard, published curves  
* Test with a single tone, a warble tone, or a band-limited white noise
* Using a simple text format supported by REW, so the result can be loaded into that tool directly
* Supports ASIO, WASAPI exclusive/shared, and Direct Sound device drivers
* Display in dB SPL or in db FS with configurable dBSPL calibration
* Apply a flat calibration curve to account for variations in headphones or speakers
* Equal-loudness testing using a 1kHz reference or a separate audio device

## How to use
The mission, should you chose to accept it, is to move the volume control up and down in small increments until you find the spot where the sound produced by Earful disappears or becomes inaudible. When you find this place, move up one step, and that will determine the lowest audibility threshold for that frequency. Repeat for all the points across the spectrum, and you'll get your entire threshold curve!

To test equal loudness at a specific volume, set Test Type to Equal Loudness, then set the Start Vol the desired volume for reference tone at 1kHz. Select the desired frequency and move volume slider up and down to get the two tones to become as close as possible in level. When 1kHz tone is playing, "REFERENCE" badge will show on the screen. The reference tone will play at the same level and at 1kHz frequency once you start the test. Please don't raise the volume to unsafe levels, even if you don't hear the tone, it can still damage your hearing at high enough levels!

To determine equal loudness curve using a second audio device, set Test Type to EQ Two Devices, then pick the two audio devices. PLEASE NOTE: both devices should be set to the same sampling rate. On the same screen, you will set the reference tone volume level. The sound will alternately come from reference and test devices. The sound will be at the frequency you select using left/right arrows, but the reference volume will be kept constant at the setting you chose. Your job is to adjust the test device tone level to sound exactly as loud as the reference tone at different frequencies. "REFERENCE" badge will show on the screen when the reference device is playing. Again, please don't raise the volume to unsafe levels, even if you don't hear the tone, it can still damage your hearing at high enough levels!

### Preparation
* Start by selecting the desired audio output device from the drop-down list
* Use headphones or speakers, although headphones are probably a better way to determine your lowest hearing threshold
* Whatever device you chose: MAKE SURE THE VOLUME IS TURNED DOWN on any preamp or DAC to a level that doesn't allow excessively loud sounds. Earful will never exceed the maximum volume setting specified on the main window, but device drivers and Windows glitches can cause very loud sounds to be reproduced. BE CAREFUL.
* Select the desired type of sound (Single Tone, Warble, or White Noise). Single Tone is a simple sine wave, similar to what was used for Fletcher-Munson curves and ISO0226 standard
* Check that the frequency range is set to what it is you want to test. You can specify smaller or larger bandwidth for testing, default is 20Hz-20kHz
* Enter more data points if you'd like a more fine-grained test. Default is 32 and this means you'll have to repeat the process of searching for audibility for each of the 32 tones to complete the test
* Make sure the start volume is set low enough not to blow your speakers or subwoofer. -60dBFS is the default setting here.

### Start the test
* Press the play button in the middle of the four arrows to start the test. The test will start with the lowest frequency you specified, at the start volume you selected.
* At any time, press the Pause button to stop playing sounds
* Move to next or previous frequency in the test by pressing Left or Right arrow buttons. The frequency plot will highlight the point where you are in the test as you do this
* To jump quickly to any point in the test, use the horizontal slider control labeled Current Point
* When at the desired test frequency, Earful will automatically start issuing the selected sounds, interrupted by a short period of silence
* If you can't hear the tones, try increasing the volume by pressing the Up arrow. If the tones are loud, press the Down button until they become barely audible
* You can use the volume slider on the right to quickly adjust the volume if the current setting is too far off. BUT PLEASE BE CAREFUL WHEN ADJUSTING UP, as you may accidentally jump to a point that's very loud. The slider will not allow setting the volume above the maximum setting specified at the start
* Keep pressing up or down buttons until you get to the point where the tones are hard to hear. If you push the down arrow once at this point and the tones become inaudible -- congratulations! You've found the lowest threshold of hearing for this frequency. Move on to the next frequency by pressing the Right button.
* 
* You can always go back and re-test any of the points you've already measured, just press the Left button to go back.
* Continue through all the points in the test. When completed, you'll see your lowest audibility threshold curve in the plot.

### After the test, data handling
* At this point, you can save the curve for later comparison, sharing with others, or for future reference. Click on Save button on the right and pick a descriptive file name. 
* Earful uses the standard frequency response text file format used by REW, and so the output of Earful measurement can be loaded directly into REW, or vice-versa.
* To compare two curves, or the one you just captured to another, click on load button and select the previously saved curve. You'll be able to load it into Data Set 1, which is the measurement data set, or Data Set 2, which is the comparison data set. A couple of comparison files are installed with Earful: Fletcher-Munson standard curve and ISO0226-2003. These represent average lower threshold of hearing across multiple people that were studied.
* Normally the second data set it automatically indexed to the lowest value in your measured data set 1. If you'd rather to index them manually, please use the + and - adjustment buttons to move the second data set up or down by one volume step size. If you check the Auto button, the automatic indexing at the lowest value will be restored.
* Clear All button on the right allows all the data to be cleared from Earful to start over. Please save any data that you may have captured up to this point, as it will be lost.

That's it for now! Hope you find Earful useful, and looking forward to your feedback.


## Changes in 1.0.11
* Changed: timing in EQ Two Devices to reduce overlap and interference between reference and test signals
* Changed: Reference device in EQ Two Devices test now always plays in both channels, Left/Right/Both control only applies to the test device

## Changes in 1.0.10
* Added Test Type selector
* Added Equal Loudness Curve test
* Added Two-device Equal Loudness test
* Added REFERENCE badge indicator
* Added Warning/Agreement text for first time users

## Changes in 1.0.9
* Added Clipping indicator
* Added Pink noise option
* Added Q setting for pink and white noise band-pass filter
* Added Left, Right, or Both ears selector

## Changes in 1.0.7
* Added support for applying headphone calibration curves for flat response (a pure frequency response of a microphone coupled to the headphones)
* Added Shift-Click to directly select any point on the plot
* Added Shift-Left/Right/Up/Down to control selecting frequency and setting volume directly from the keyboard
* Fixed exceptions when ASIO or WASAPI drivers are not supported (for example, under Wine on Linux)
* Fixed data points being set to the previous point volume setting when the actual value is -120dB
 
## Changes in 1.0.6
* Fixed labels not cleared on the graph after the data is cleared
* Fixed WASAPI exclusive mode not turning on for some audio drivers
* Fixed automatic switch between shared/exclusive mode when the checkbox is changed
* Added a little delay when reacting to previous/next buttons or the slider to reduce sound glitching
* Fixed first data point value not set correctly in saved data after reloading on start-up of Earful

## Changes in 1.0.5
* Fixed many audio threads created when moving around the chart
* Added screen shot button
* Added current step counter display
* Fixed clearing the first data point when data is cleared by setting volume slider to starting volume
* Added saving current settings on exit and reloading on start


## Changes in 1.0.4
* Speeded up audio signal generation for slower processors

## Changes in 1.0.3
* Added dBSPL display option
* Added SPL Meter calibration
* Changed data file loader to use proper regional settings for decimal separator

## Changes in 1.0.2
* The initial public beta release of Earful

___
{% include links.html %}
