---
title: Settings
tags: [settings]
keywords: settings, configuration, customization, fft, gain, enable, disable
last_updated: September 4, 2019
summary: "Version 1b of DeltaWave is the initial beta release of this software. Use at your own risk!"
sidebar: mydoc_sidebar
permalink: settings.html
folder: mydoc
comments: true
---

## Configuration Settings (Setup)

Configuration settings are available by clicking the gear icon at the top right of DeltaWave window.

![waveform](images/img6.png)

* Any changes you make to the settings are automatically updated when you close the Setup window
* Settings are automatically saved and reloaded the next time you start DeltaWave
* You can optionally save current settings in a separate file by selecting File menu on DeltaWave main window and chosing Save Settings
* Setting changes are applied the next time you click on Match or Show button

### General Settings

Setting  | Description
-------- | -----------
Resample| When two selected files are not sampled at the same frequency, this option tells DeltaWave what to do to match them. When not checked, the default is to down sample to the lowest rate of the two files, equivalent to **Auto Downsample**. **Auto Upsample** will automatically upsample the lower rate file to the higher rate one. A choice of a specific rate (44.1kHz-384kHz) will cause DeltaWave to resample any of the files that are not at the specified rate. 
Correct Phase Drift | If clock drift is detected during processing, this tells DeltaWave to attempt to adjust this out. This allows two files recoreded with slightly differing clocks to be properly matched up. On is the default setting.
Match Gain | Compute and adjust the levels of the two files, if different. On is the default setting.
Prompt to invert phase | If two files are detected to be inverted relative to each other, this will prompt you to confirm if you want to correct this. The default is off, meaning DeltaWave will just correct the phase without asking you.
Dither to original bit size | When selected, the processed files (normally handled in double-floating point format) will be dithered to the original bit size, ensuring the same precision of samples as in the original files.
Auto-trim start & end | This will automatically remove any silence at the beggining or end of both files. After the matching operation is performed, any contiguous samples at the start or end of both files will be removed as long as their difference far exceeds the average diffrence between samples in the rest of the file. This feature will never remove more than about 5 seconds of data. 

### Spectrogram Settings

Setting  | Description
-------- | -----------
FFT Size | Larger size increases frequency resolution, but slows down processing. Very large size can result in a very slow display of the spectrogram plot
Window   | Different windows will have slightly different effect on FFT processing. Hann is probably the safest window to use for most tasks, although BlackmanHarris7, Kaiser, Taylor and a few others have some interesting characteristics for digging deep into the noise floor.
Steps    | Number of time steps (horizontal axis) to display. Larger number will result in greater time resolution, but also in many more FFT calculations, slowing down processing and the spectrogram plot
Interpolate | This will try to fill in missing data between points in the plot by interpolation. This has the effect of smoothing out sudden jumps between frequency bins, especially when zoomed in.


### Resampling Settings

Setting  | Description
-------- | -----------
FFT Size | Not used
Window   | Different windows will have slightly different effect on resampling processing
Auto-resample for audio playback | When the audio device doesn't support the sample rate or bit rate of the loaded waveform, automatically resample it to the appropriate format before playing. If this is not selected, you'll see a message asking if it's OK to resample when pressing any of the play buttons.


### Spectrum Settings

Setting  | Description
-------- | -----------
FFT Size | Larger size increases frequency resolution, but slows down processing 
Window   |  Different windows will have slightly different effect on FFT processing. Hann is probably the safest window to use for most tasks, although BlackmanHarris7, Kaiser, Taylor and a few others have some interesting characteristics for digging deep into the noise floor
Peak Hold |  Instead of averaging each FFT window, the plot will show maximum (peak-hold) value for that frequency bin
Reduce Spectral Leakage | This is useful when examining captures of a simple signal, such as a sine wave. The feature works by selecting an approrpiate FFT window overlap so as to reduce spectral leakage effect of FFT. This helps see much deeper into the noise floor and makes a simple sinewave appear much narrower, and less spread-out in the spectrum plot than would be the case with the standard overlap sizing.

### Cepstrum Settings

Setting  | Description
-------- | -----------
FFT Size | Larger size increases frequency resolution, but slows down processing 
Window   | Different windows will have slightly different effect on FFT processing. Hann is probably the safest window to use for most tasks, although BlackmanHarris7, Kaiser, Taylor and a few others have some interesting characteristics for digging deep into the noise floor


### Filters

Setting  | Description
-------- | -----------
Filter Type | **FIR** or **IIR**. FIR filters have a linear phase response
Filter Size | Number of taps in FIR or IIR filters 
Window   | Different windows will have slightly different effect on FFT processing. Hann is probably the safest window to use for most tasks, although BlackmanHarris7, Kaiser, Taylor and a few others have some interesting characteristics for digging deep into the noise floor

### Non-Linear Calibration

Setting  | Description
-------- | -----------
Level EQ | When checked, this will compute the average difference between the waveforms and use this to correct the Comparison waveform amplitude. In effect, this applies a graphical EQ with the precision frequency equal to one frequency bin. This can correct for the effect of filters and non-linear frequency response curves of a device.
Phase EQ | When checked, this will compute the average difference in phase between the two waveforms, and then apply this as a phase-only correction to the comparison waveform. In effect, this can correct for various repeatable timing/phase errors, including those caused by filters.
Non-linear Drift Correction | This feature works entirely in the time domain, computing non-linear clock drift errors and correcting them in the Comparison waveform. This should lead to a much flatter, closer to zero, Drift Error plot.
EQ FFT Size | Used to determine the FFT size used for Level EQ and Phase EQ operations
EQ From/to | Select the bandwidth where Level and Phase EQ operations are applied. All frequencies below **from** and above **to** will not be corrected. Select **(all)** in the **to** setting to include all available frequencies.
EQ Threshold | This sets the the lower limit for the frequency bin amplitudes when correcting for Level and Phase EQ. Any frequencies with amplitudes below this limit will not be corrected.

### Display Options

Setting  | Description
-------- | -----------
List | Select the options from the list that you would want to see as the result of the Match operation in DeltaWave. Any items that are not checked will not show as a tab on the main screen. The values and the plot related to the hidden tabs will also not be computed, so the fewer tabs are visible, the faster you'll see the result on the screen. After making any items visible, you'll need to re-run the Match operation to update the plot under the newly visible tabs.
Calculate MD5 Hash | When selected this will compute an MD5 hash for each of the two files. The value will be included in the Results text. A signature value that can be used to verify that two results were produced using the same files. If the MD5 hashes don't match between the two files, the files are different.

### DSD Conversion

Setting  | Description
-------- | -----------
Resample To | In order to analyze DSD files, DeltaWave needs to convert them to PCM. This selects the desired PCM rate to convert DSD files.
Cut Frequency | DSD contains a large amount of quantization noise that is normally removed by a low-pass filter. This setting specifies where to place this cut-off filter. Anywhere above 24kHz or so would be reasonable.
Transition BW | Specifies the bandwidth of the low-pass filter transition. The smaller the bandwidth, the sharper the filter.

___
{% include links.html %}
