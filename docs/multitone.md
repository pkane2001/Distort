---
title: Multitone - Loopback Analyzer for Audio
tags: [Multitone]
keywords: release notes, announcements, what's new, new features
last_updated: November 7, 2022
summary: "Multitone is currently in beta test. Use at your own risk!"
sidebar: mydoc_sidebar
permalink: multitone.html
folder: mydoc
toc: true
comments: true
---

![multitone1](images/multitone1.png)

![multitone2](images/multitone2.png)

![multitone3](images/multitone3.png)

<br>
<br>

## Download Multitone
<a href="MultitoneSetup.zip">Download Multitone for 64-bit Windows v1.0.56  &nbsp;&nbsp; <input type="image" id="ma" alt="Multitone" src="images/multitone_logo.png" width="30" align="top" />   </a>

<input type="hidden" id="version" name="version" value="1.0.56"/>



## You may also be interested in these:
* <a href="https://deltaw.org" target="_blank">DeltaWave</a> - Audio null analyzer and audibility tester
* <a href="https://distortaudio.org" target="_blank">DISTORT</a> - Your personal simulation of what various distortions do to audio
* <a href="https://distortaudio.org/pkharmonic.html">PKHarmonic VST Plugin </a> - VST Plugin to add the desired level of 2nd and other harmonics 
* <a href="https://distortaudio.org/earful.html">Earful </a> - An audiophile Hearing Test 
<br>

## Support forum
During the development and beta-testing of Multitone Analyzer, you can report issues, ask questions and make suggestions on the ASR forum [here](https://www.audiosciencereview.com/forum/index.php?threads/beta-test-multitone-loopback-analyzer-software.27844/).

## What is it?
Multitone Analyzer is an app designed to explore audio electronics performance by producing quick measurements using a simple loop-back configuration. MA produces a specific set of test tones that are sent to a digital-to-analog converter (DAC) that are then passed through one or more analog components and then received by MA and analyzed. MA both, plays the signals and records them for analysis. DAC and ADC are required for this to work.

* Measurements that MA can produce: TD+N, IMD, N+D, delay, clock drift, frequency response, etc.
* Audio support for WASAPI, ASIO, and Direct Audio devices with sampling rates of up to 384kHz/32 bits
* Test signals: arbitrarily large multi-tone signal, simple sine waves, two-tone IMD test signals, 3-tone IMD test signals, square wave, triangle wave
* FFT sizes of up to 1M
* For distortion measurements a range of frequencies to measure can be selected

## How <u>not</u> to use it!
Don't use this with your speakers or headphones! The test signals are designed for electronic device testing only, and levels and frequencies of the test can be enough to cause damage to the equipment, or worse yet, your ears. Be warned!

## How to use it
* Make sure a DAC and an ADC are connected and working with the PC running Multitone Analyzer. Connect the DAC output to another device you want to test, and then connect the output of that (or the output of the DAC) to the input of the ADC
* Select the correct devices from the two drop-down lists at the top of MA screen
* Select the desired test signal, pick a level and press the red record button
* Let Multitone Analyzer do the rest. The sequence will be Generate, Record, and then Process. Results will be displayed when the recorded signal is captured and analyzed

![multitone](images/multitone4.png)

## A few things to know
1. All the lists and drop-downs on the main MA screen are editable. You can change frequencies, amplitude ranges, or type in frequencies that are not already in the drop down. In effect, you can create completely new tests consisting of different tone combinations.
2. The little gear button at top right provides a few useful settings and is worth checking out
3. If you're familiar with my DeltaWave or Distort apps, you can use the same key and mouse combinations in the charts to zoom-in, pan around, or even draw your own annotations
4. Larger FFT sizes might take a bit of time to generate the first time you use them. Be patient the very first time, as the next time you use the same FFT size, it will go a lot quicker. This is true even after you close and restart MA, or even restart your computer. It'll be a bit slow the very first time.
5. Both, DAC and ADC must use the same sampling rate. Make sure you configure this in Windows audio device settings. MA will detect the correct sampling rate for the device and use it for WASAPI devices. For ASIO devices, please set the desired sampling rate in settings, under the gear icon.

![multitone](images/multitone-settings.png)


## Tips to make it work better
1. Larger FFT sizes are necessary for higher resolution frequency analysis. This is especially true for multi-tone testing. If the tones in the result are overlapping, touching, or look deformed, increase FFT size to make sure they are properly resolved. For anything more than 10 tone signal, I recommend using 1M FFT
2. Larger sampling rates will take time to capture signal when processing with the same FFT size. 96kHz capture will be twice as fast as 48kHz capture. Larger FFT sizes will generate and record a longer test signal than shorter FFT sizes.
3. If you're not in a rush, it's nearly always better to set the FFT size to the largest available
4. The Frequency Response chart is only generated with large-size multi-tone test signals (greater than 5 tones). It will be blank for all other test signals.

![multitone](images/multitone5.png)

## Adding custom test signals
You can design a completely custom test signal by just editing in the parameters on the MA main window. To save the new test, press the + button next to the edit box. The test will be available next time you restart Multitone Analyzer, just pick it from the drop-down list. If you need to remove a previously saved custom test, select it from the list and click the '-' button next to the edit box.

The test tone specification format is fairly simple: test name, followed by one or more frequencies, optionally followed by amplitude ratios.

The name of new test signal must contain no spaces. Frequency can be entered using Hz or kHz or k as a suffix: for example 100Hz, 0.1kHz, or 0.1k are all equivalent. If a modifier is omitted, Hz is assumed.

### Modifying existing test signals
You can change the parameters of any of the existing test signals and save that as a new test.

For example, starting with ``Multitone 32``, you can change it to ``Multitone 55``. The name of the signal, Multitone, must not be changed in this case but you can change the number of tones to any desired value.

Or, starting with ``SMPTE 60Hz/7k 4:1`` you can modify the two frequencies or the amplitude ratios to produce new test signals. Or you can even add another frequency or two into the mix.

```
SMPTE 100Hz/7.123k 4:1
SMPTE 25Hz/7k 5:1
SMPTE 30/60/1k/7k/13k 4:4:1:1
etc.
```
Similarly, you can modify the standard DIN tests:

```
DIN 300Hz/7k 4:1
DIN 250/1k/7k 4:1:1
```

### A single sinewave at a specific frequency

Format: ``Name freq``

Examples:

```
Sin_100hz 100
MySine 100Hz
NewTest 15kHz
Test_15k 15k
```

### Multiple sinewaves

Multiple sine frequencies can be specified by separataing them with a forward slash:

Format: ``Name freq1/freq2/.../freqN``

If you want to change the amplitude ratios between the multiple frequencies, these can be added after the frequency list, separated by ':'

Format: ``Name freq1/freq2/.../freqN ratio1:ratio2:...:ratioN``

Ratio 4:1 for example specifies that the first sinewave will have 4x the amplitude of the second one. If ratios are omitted, all sinewaves specified will have the same amplitudes (equivalent to 1:1:...:1)

Examples:

```
MT_Test1 100Hz/13kHz
MT_Test2 20/100/13k/13.1k/15k
MT_Test3 100Hz/13kHz 4:1
MT_Test4 20/100/13k/13.1k/15k 1:4:1:1:1
```

### Adding a square wave
You can specify *at most one* square wave frequency in your test signal. This is done by preceding the very first frequency with 'sq:'. One square wave can be mixed with multiple sinewaves, if desired.

Examples:
```
SQT_OneSqWave sq:100.5Hz
SQT_OneSqWave_and_3_sines sq:100/13k/13.1k/15k
SQT_Test3 sq:1000Hz/13kHz 4:1
SQT_Test4 20/100/13k/13.1k/15k 1:4:1:1:1
```

## Configuring variable expressions
Multitone 1.0.49 introduced the ability to customize title and results display with your own calculations and formatting. This feature is documented <a href="https://distortaudio.org/multitone-exp.html">here</a>.

<br>


## Changes in 1.0.56
* Add: RMS and RMS(A) result display
* Add: IMD (multitone) distortion panel that includes TD+N, SFDR, Noise, IMD, ENOB and other results
* Fix: Missing information text on copy plot to clipboard
* Change: backround display for the distortion information panel
* Change: auto-adjust result button display to fit all the text
* Change: Improved IMD calculation now works with multitones with up to 64 tones (was max of 5 previously)


## Changes in 1.0.55
* Add: support for measuring difference between two channels ("L-R" input selector). Added to spectrum, frequency response, phase, and waveform plots

## Changes in 1.0.54
* Change: improved method to find the initial sample alignment between test signal and captured waveform
* Change: THD/distortion panel now shows THD relative to the fundamental, regardless of the selected units
* Fix: calibration file was not applied in spectrum plot after capture
* Fix: phase plot custom titles not preserved after measurement

## Changes in 1.0.53
* Add: support for DSD test signal playback over DOP, supporting DSD64, DSD128, DSD256
* Add: phase plot, calculated when using multitone test signals and the same ADC/DAC sample rate
* Add: Higher sampling rates up to 768k (possibly higher, if your device(s) support it)
* Add: File drag-and-drop (on test signal drop-down) feature to measure files without DAC/ADC loopback
* Fix: when displaying spectrum captured in stereo mode, show full bandwidth of the captured signal

## Changes in 1.0.50
* Add: support for dBV, dBW, V, and W display units with Amplitude Voltage (FS) and Resistance calibration settings
* Add: support for creating custom Frequency-modulated test signals and adding a couple of test signals to the drop-down list
* Add: during measurement you can switch to the Waveform plot to see a live preview of the waveform being captured
* Fix: reprocessed data from history entry didn't quite match the original measurements due to lower number of averages
* Fix: history click/unclick sometimes selected the previous entry even when the checkbox was not clicked
* Fix: color selection dropdown in history sometimes required two clicks
* Fix: switching to Spectrum plot after a sweep, but with the sweep still selected, and then performing a measurement would do a spectrum analysis instead of the sweep

**Changes in 1.0.49**
* Add: Amplitude Spectrum Density display option (scales spectrum display per sqrt(Hz)) to remove the effect of FFT gain on noise floor
* Add: ability to create new, custom display variables in Results window
* Fix: level meter fluctuates on steady tone below 5Hz
* Fix: short frequency range multitone test signal can cause a crash in generate function
* Fix: hang if frequency sweep starts with 0Hz
* Change: remove detection of noisy measurements in sweeps




**Changes in 1.0.48**
* Add: new test signal Silence (can be dithered)
* Add: setting to position plot legend in any of the four corners
* Fix: error when displaying a history result with single channel, but requesting the other channel
* Fix: settings panel resizes to larger when window is maximized and Multitone closed in that state
* Fix: switching from External test signal to another one records only silence

**Changes in 1.0.47**
* Add: capture, measure and compare any two channels from the ADC
* Add: frequency and level sweeps comparing two capture channels
* Add: results window can display results for both channels, or a single channel can be selected for comparison
* Change: ASIO buffer management to speed up data processing. Smaller ASIO buffer size is now supported.
* Fix: wrong result when applying calibration file


## Changes in 1.0.45
* Add: Maximum number of history entries setting
* Add: Export/Import history data in *.mth file
* Fix: SNR was displayed with - sign
* Fix: SNR was computed incorrectly for different frequency ranges
* Fix: data not removed from plot when corresponding history entry is deleted
* Fix: error when clicking on Selection header when nothing is selected in history
* Fix: latest measurement selected from history is wrong color and missing series label
* Fix: new measurements don't appear in comparison results when selected


**Changes in 1.0.43**
* Add: Measurement 1 and 2 selector for sweeps. Allows any combination of two measurements to be plotted against each other
* Add: Measurement value selector in Results display to customize the reported values
* Add: History measurement/comparison selector in Results display to compare the current result to any number of previous ones, side by side
* Add: Fundamental amplitude result
* Add: SFDR measurement frequency


**Changes in 1.0.42**
* Add: Results window display
* Add: all settings load and save options
* Add: Index to (dB) property
* Add: Index and marker settings to Frequency Response and Frequency Sweep plots
* Add: Refresh all plots button
* Add: SFDR measurement to one-tone test signal results
* Add: date/time column to history, separate from label
* Change: history selection behavior (check mark always adds to the plot, double-click causes recalculation of all results for that entry)
* Change: Index to and Index at settings apply to all spectrum plots and measurements, not just history
* Fix: Floating point files saved to disk now have the correct IEEE format (3) setting
* Fix: axes labels sometimes could be displayed multiple times, overlapping, when changing settings

**Changes in 1.0.41**
* Add: support for additional channels with ASIO and WASAPI multi-channel drivers
* Add: sawtooth and reverse-sawtooth test signals
* Add: cool-down setting for sweeps and repeated tests
* Add: property settings panels for Waveform and Frequency response plots
* Fix: low-level (LSB) errors with ASIO and WASAPI drivers due to 24-bit truncation in 32-bit floating point
* Fix: scaling of the waveform plot when different sampling rates are used for playback and recording

**Changes in 1.0.38**
* Fix: channel selector not always restored correctly on start-up
* Fix: frequency sweep shows wrong level on the status bar and sweep output level changes from the selected play gain during the sweep


**Changes in 1.0.37**
* Fix: regression in .37 - play gain applied twice
* 
**Changes in 1.0.36**
* Fix: when using file as source, changing file didn't update the test signal due to caching
* Fix: apply dither to source file if play gain setting is adjusted and dither option is enabled
* Fix: adjust 24 bit scaling to not exceed full scale when converting to/from floating point
* Fix: save window position and other settings when changing some parameters on the main screen
* Add: frequency vs TD+N and IMD sweep
* Add: option to sweep one or all frequencies


**Changes in 1.0.35**
* Fix: History color picker causing a hang
* Add: setting to show/hide THD display panel
* Add: setting to index all history plots at the same frequency
* Add: Periodic White and Pink noise test signals tied to the current FFT frequency
* Add: Automatic looping of external files when used as a test signal
* Fix: add back the value of 1 to the clipboard scale setting in the property list


**Changes in 1.0.34**
* Fix: Waveform plot is now displayed (was missing in .32)
* Fix: Remove unnecessary units next to each axis label (dB, etc.)
* Fix: re-enable processing External data
* Change: adjust font sizes (title, and measurements)
* Add: axes labels to all charts
* Fix: dither applied correctly for different bit-sizes
* Fix: processing THD and harmonics detection in the presence of large noise in LF
* Fix: restoring hybrid/coherently averaged data from history displayed noisy data
* Add: selector save generated test files in 32- and 64-bit floating point
* Add: automatic update of displayed plots when changing chart properties with no need to re-capture data
* Change: marker setting now allows for multiple markers to be added to the same plot

**Changes in 1.0.32**
* Add: Spectrum and IMD Sweep charts now can be configured in the main window, using a property sheet
* Add: Marker line can be added to the spectrum line to indicate a specific frequency
* Add: Spectrum and Sweep chart titles can be customized
* Add: X and Y axes labels on Spectrum and IMD chart
* Add: Spectrum and Sweep chart font size can be adjusted
* Add: Image copy to clipboard, text rearranged to not cover up the plot area, additional values added
* Change: Sweep cylce starts with 1 instead of 0
* Change: averages are now computed on all available data instead of doing one at a time (faster, all averages always complete)
* Change: IMD Sweep window now automatically scales with data, individual measurements are indicated on the chart
* Change: in low-contrast display, plot background is now white, not gray. Other colors adjusted for better visibility
* Fix: IMD Sweep X-axis didn't show fractions of dB when zoomed-in
* Fix: average overlap in settings didn't work with decimal comma separator
* Fix: Input WASAPI driver wasn't always correctly restored on start


**Changes in 1.0.31**
** Fix: hang or crash with certain ASIO drivers when ending recording or closing Multitone

**Changes in 1.0.30**
* Fix: regression from .29 -- play gain is applied twice 
* Level sweep isn't displaying results


**Changes in 1.0.29**
* Add: display RMS and dBA value display when not using discrete tones as the test signal
* Add: white and pink noise to test signal list
* Add: restore main Multitone window position and size on restart
* Change: some minor UI changes (labels, tooltips, fonts, etc.)
* Change: allow test signal generation to be interrupted by stop button
* Change: don't regenerate the same test signal if no parameters changed between test runs
* Change: reduce memory pressure by not making copies of the original test waveform
* Change: move frequency response curve to be around 0dB in the plot
* Change: clear zoom levels when switching FFT sizes to allow the plot to auto-scale
* Change: the state of Show 1 and Show 2 checks automatically apply for future measurements
* Change: 'Detect driver changes' will now also disable testing of connected ASIO driver on start-up when not checked
* Change: frequency response plot stays in focus when running new measurements (switched to spectrum plot before)
* Fix: record second channel (R) with ASIO devices (reported issue with MADIFace ASIO driver)
* Fix: selected history items now remain checked when closing/re-opening history window
* Fix: history items show fully averaged result (previously only first FFT-sized average was displayed)
* Fix: allow smaller than 64k FFT sizes to be entered for measurements by typing them in

**Changes in 1.0.28**
* Fix: preview window now shows the full audio spectrum from 20Hz to 24kHz
* Fix: occasional OxyPlot exception message displayed in the plot area
* Fix: AES17 notch applied incorrectly on dual-tone test signals

**Changes in 1.0.27**
* Add: Support for different sampling rates for record and play devices
* Add: ASIO sample rates can now be specified separately, one for input, the other for output
* Add: WASAPI configuration/control panel for in and out devices
* Change: THD+N is now computed over the selected frequency range (previously over the entire bandwidth)
* Fix: Preview window occasional glitch reduced
* Add: High/low contrast display option/color scheme selector
* Change: Red-X on the main window will now clear collected averages and continue measurement for any left-over averages any time its pressed during measurement
* Change: ASIO devices that are not connected to the PC will no longer be listed in the device list
* Change: Dither can now be specified in fractional bits (as in 22.5)

**Changes in 1.0.26**
* Fix: Direct Sound driver selector broken in recent updates

**Changes in 1.0.25**
* Fix: WASAPI Exclusive mode now works with best available bit setting (previously only 16 bits)

**Changes in 1.0.24**
* Fix & Change: WASAPI Shared mode setting renamed to WASAPI Exclusive. The meaning was previously swapped
* Fix: Some ASIO drivers couldn't be mixed with WASAPI or other ASIO drivers because each driver tried to open channels for input and output
  
**Changes in 1.0.22**
* Change: better detect the start of the playback waveform by measuring noise floor
* Add: option to turn off audio new/removed driver detection to alleviate too many notifications caused by some drivers
* Fix: THD is now calculated within the selected frequency range (was over the whole bandwidth)
* Change: optimizations to allow for smaller ASIO buffer sizes, faster sampling rates, and better performance on slower computers

**Changes in 1.0.19**
* Fixed: occasional stutter at the end of audio capture
* Fixed: waveform tab is now showing the correct captured waveform (was broken in .17)
* Fixed: selected audio driver changing when sample rate is changed by ASIO driver or some other changes occur

**Changes in 1.0.18**
* Fixed: Average overlap setting used US-style decimal point causing errors in regions where decimal comma is used
* Fixed: Occasional hangs when using certain ASIO drivers
* Changed: When using averaging, the results are no longer recomputed when capture is completed, saving time

**Changes in 1.0.17**
* Added: AES17 spec notch filter for THD+N measurements
* Added: Support for REW-style input device calibration file
* Changed: display running average spectrum while collecting data
* Reverted: ASIO channel management change in .16 caused ASIO recording to fail for some users

**Changes in 1.0.16**
* Added: Amplitude (in-coherent), Coherent, and Hybrid averaging and related computations
* Added: Average overlap % selector
* Added: Repeat option to continually repeat the selected measurement
* Added: History color and label editing capability, delete selected (or all) history entries
* Added: Kaiser 6, 12, and Chebyshev 200 FFT Windows
* Added: Option to save generated test signal to a 64-bit WAV file
* Added: Noise measurement to harmonic distortion panel
* Changed: External test source fundamental tone extraction
* Changed: IMD computation to include SMPTE/DIN/CCIF
* Changed: Harmonic amplitudes are now always displayed relative to the fundamental, regardless of dBr setting
* Fixed: ASIO input selector for channels might cause a crash with the Right channel selected

**Changes in 1.0.15**
* Added: Copy current plot to the clipboard with scaling factor configurable in settings

**Changes in 1.0.14**
* Added: J-Test 24 and J-Test 16 test signals for jitter measurements
* Added: Option to change frequency axis display between log and linear
* Added: Option to select how many harmonic components to show on the display
* Added: Automatic numbering of harmonics in the frequency plot
* Changed: IMD calculations improved accuracy and switched to using more common calculations (SMPTE and CCIF)
* Changed: Level/IMD sweep plot X-axis will now show test signal amplitude in dBFS (previously showed measured signal)


___
{% include links.html %}
