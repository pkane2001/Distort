---
title: Release notes
tags: [getting_started]
keywords: release notes, announcements, what's new, new features
last_updated: July 15, 2019
summary: "Version 1.0b of DeltaWave is the initial beta release of this software. Use at your own risk!"
sidebar: mydoc_sidebar
permalink: release_notes_1.0b.html
folder: mydoc
comments: true
---

## What is it?
DeltaWave is an experimental software built to allow detailed comparison of two different captures of the same audio signal.
It was inspired by the idea of [Audio DiffMaker](http://www.libinst.com/Audio%20DiffMaker.htm), but it is a completely new piece of software, written from scratch. No parts of Audio DiffMaker were used in DeltaWave. Calculations and algorithms used in DeltaWave are also different, and results are more than likely not agree between these two programs. As I was never successful at using *Audio DiffMaker* but wanted to, DeltaWave was born.

## Is it free?
DeltaWave is provided to you free of charge, and contains no advertisements or in-program purchases.

This is an early beta version of the software and is set to expire in 60 days. Please check this website before then to get an updated copy!

## What can I do with it?
As the most basic function, DeltaWave allows an objective measure of how different two captures of the same audio signal might be.

Examples where this can be useful include:

* Compare analog and digital captures of the same track
* Compare two different digital formats of the same track (different number of bits, different sampling frequency, different filtering, or even difference between PCM and DSD formatted files)
* Determine how much of a difference an electronic component makes on the output of an audio system
  * Audio interconnects
  * Power cables
  * Digital/USB interconnects
  * Pre-amps
  * DACs
  * Amplifiers
  * etc.
*  Visualize audio waveforms using:
   *  Zoomable wave comparison plots
   *  FFT Spectrum analysis charts
   *  Cepstrum analysis
   *  Spectrograms
   *  Phase differences
* Listen to each track, individually
* Listen to the difference track after subtracting the two
* Write out the difference track as 32-bit WAV file for external analysis

## Changes in 1.0.47b
* Put back group delay plot removed in v.46
* Added separate FFT Window option to non-linear EQ (previously used the same window as Spectrum settings)
* Improved jitter error result with simple waveform measurements
* Fixed the amplitude increasing by x4 when using simple waveform measurements combined with drift correction


## Changes in 1.0.46b
* Added non-linearity plot
* Added legend and harmonic arrows option to matched spectrum plot
* Clock Drift correction now works in simple waveform measurement mode
* Fixed Kaiser window not producing correct results when FFT size is equal to the number of samples
* Turned off curve fitting in phase plot (made the plot too busy and often looked chaotic)
* Improved the quality of up/down sampling, added appropriate level of dither for the original bit size
* Changed lower limit on plots to -400dB from -300dB

## Changes in 1.0.45b
* Added option to align and compare simple periodic waveforms
* Added THD, THD+N, and Dynamic Range calculation when measuring simple sine wave
* Added overlay options to time-domain waveform plots

## Changes in 1.0.44b
* Fix for index out of bounds when downsampling 48k to 44.1k files

## Changes in 1.0.43b
* Fix for phase and spectrum plots having very small differences between runs
* Fix for volume going down after a second of play from the main window

## Changes in 1.0.42b
* Fix Non-linear EQ not working
* Fix artifacts displayed at the very end of a spectrogram
* Add color palette selection for Spectrograms with many to choose from
* Add the ability to overlay spectrum plots from previous match runs, including those loaded from disk


## Changes in 1.0.40b
Fixing a few regression items from .39:
* Re-enable dynamic volume adjustment while playing form the main window
* Fix wrong color used in Spectrogram when all values are the same (e.g., 0dB)
* Fix "Stopped! Matrix dimensions must agree: op1 is ..., op2 is ..." error

## Changes in 1.0.39b
* Support for processing, playing, and comparing/exporting stereo files
* Added new selector for filters to filter Ref, Comp, Ref+Comp
* Added amplitude range selector for Spectrogram plots
* Improved FIR filters (LP, HP, and Notch) with better out-of-band rejection
* Improved aliasing behavior resampling operation to reduce artifacts
* Cleaned up some control UI sizing and painting issues
* Proper application of all the new FFT Windows introduced in 1.0.38


## Changes in 1.0.38b
* Major changes in FFT Windowing routines for improved accuracy at very low levels (below -180dB)
* Additional FFT Window selections, including
    * Blackman-Harris 7 term
    * Chebyshev
    * Sum of Cosines 23-term
    * Kaiser
    * Taylor
    * Improvements to existing windows precision  
* Added Spectrum setting to reduce spectral leakage to help reduce the averaging effect of overlap-add FFT
* Added Edit menu option to reset all settings to their defaults
* Added Manual Adjustment window selector to chose what parameters to use for optimization
* Fixed a bug in the Manual Adjustment window that occasionally reset the offset parameter
* Improved look and feel of the UI when running on high-DPI displays, e.g., on Windows 10
* Added WAV file export option support for 64-bit floating point PCM samples
* Improved upsampling/down-sampling algorithms
* Fixed a bug that caused Original Spectra window not to refresh when changing certain display options

## Changes in 1.0.37b
* Fixed an error when applying two filters of the same kind (LP/LP or HP/HP) one at start and one at end of processing
* Changed the choice of FFT Window function to improve Non-linear EQ (level and phase) precision

## Changes in 1.0.36b
* Fixed an error when processing Phase EQ with too few samples for the FFT size
* Fixed an error where Phase EQ was applied when 'Show' operation was requested

## Changes in 1.0.35b
* Fixed processing of minimum/maximum frequency and threshold when performing non-linear Phase EQ

## Changes in 1.0.34b
* Improved phase unwrap logic
* Changed Phase EQ to apply full spectrum EQ instead of curve
* Modified curve fitting algorithm to ignore lower frequencies if there is significant jumps there

## Changes in 1.0.33b
* Added non-linear phase correction option (correcting for variable group delays)
* Results tab now shows group delays in seconds and degrees for a few chosen frequencies
* Modified delta phase plot to show phase before and after correction, as well as the measured group delay when computed
* Changed the phase unwrap logic to produce a smoother curve
* Added support for reading MP3 files
* Added option to apply current volume control settings to the Reference and Comparison waveforms (under Process Menu)
* Added one level Undo option to undo previous matching/processing operation

## Changes in 1.0.32b
* Fixed a bug with FLAC reader library that could cause 'echos' in place of zero-valued samples
* Added Process->DownShift Frequency option to allow listening to ultrasonic frequencies
* Added Jitter metric measuring timing error
* Added View->Status Bar options to control information displayed in the status bar
* Added Non-linear drift correction in Settings to allow the removal of residual non-linear clock-drift errors
* Changed Notch filter implementation for greater rejection
* Added labels displaying zoom setting in correct units in custom Zoom dialog

## Changes in 1.0.31b
* Fixed spectrum plot oscillations after a sharp filter
* Fixed incorrect offset calculated with some hires files
* Added Comparison file name to the list of recently used
* Fixed volume setting not being remembered when switching between Ref/Comp/Delta files

## Changes in 1.0.30b
* Fixed forced resample option (broken in .28b)

## Changes in 1.0.29b
* Fixed Spectrogram plots scaling problem introduced in the previous build

## Changes in 1.0.28b
* Fixed trim calculation to allow at least 5 seconds of mismatch at the file start (previous version reduced this to 1 sec)
* Fixed resampling option from Manual Adjustment window when caching is enabled
* Added the number of clipped samples indicator and Correct Clipping process menu option to rescale to 0dBFS or less

## Changes in 1.0.27b
* Added upsample/downsample rate selection in settings
* Pressing play button next to any other file while one is already playing will continue playing the new file where the previous one left off
* Improved stability of FFT calculations to eliminate differences in the least significant digits of double-precision numbers
* Added a list of recently used files to the File menu
* Changed the unlock button to remember a separate zoom level for each of the charts
* Fixed the issue with zoom level resetting when using Manual Adjustment tool
* Fixed offset value set to zero when using Cached data for the first time in Manual Adjustment tool
* Improved the accuracy of cross-correlation computation in the presence of a large clock drift
* Fixed the condition for prompting to use alternate drift correction algorithm when using higher resolution sampling rates

## Changes in 1.0.26b
* Changed silence trim function to also auto-trim mismatched parts of the waveforms front and back (up to 5 secs each)
* Added Correlated Null chart showing average Correlated Null over time
* Improved precision of offset and drift calculation
* Changed the gain difference calculation to improve performance with narrow filters
* Improved match performance with less than 10 seconds of waveform data
* Added more decimal places to the display in the Manual Adjustments results table

## Changes in 1.0.25b
* Added error % distribution chart
* Added gain error over time chart
* Improved sub-sample offset calculation to reduce residual drift error
* Added tab selection menu item
* Added option to apply filters before or after the calculations
* Changed clock drift error raw plot to show actual error instead of linear interpolation
* Changed sample trimming to remove any data from time that doesn't have corresponding data in the other waveform
* Changed the method used to calculate gain differences to include more of the waveform data
 
## Changes in 1.0.24b
* Added support for IIR and FIR filters in settings
* Improved ringing performance of LP/HP/Notch filters
* Improved drift calculation precision
* Removed the precision setting (always set to 30 now)
* Added time axis display in samples, in addition to second, and microseconds
* Added data caching option to the Manual Adjustment screen to speed up processing
* Fixed clock drift plot to show last calculated drift instead of next to last

## Changes in 1.0.23b
* Added Quality of Fit indicator
* Added support for AIFF file format
* Added Clock Drift plot
* Replaced stock resamplers with my own FFT versions for better accuracy
* Added axis lock/unlock option for each of the plots
  
## Changes in 1.0.22b
* Added manual adjustments window with a manual and automatic tester/optimizer of null parameters (**Process->Manual Adjustments...** menu)
* Added option for exporting WAV data in various combinations (**File->Export WAV File...** menu)
* Added Unwrap Phase option (**View->Charts->Unwrap Phase** menu) for delta phase display
* Optimized for precision in calculations, ensuring only significant digits are used in processing, increased precision
* Changed the logic to automatically switch to the alternative drift correction algorithm if the default one doesn't produce a valid result
* Added an error message and a stop when a proper match is not found
* Fixed the position selector for Lissajous plot
* Added DC value and all the computed values in raw format to the Results tab
  
## Changes in 1.0.21b
* Fixed some issues with annotations, improved readability and formatting
* Fixed an issue where a few samples were not read at the end of some WAV files
* Added microsecond display option to show detailed time information on the X axis

## Changes in 1.0.20b
* Better nulls with Audacity-processed 16-bit files
* Read 24- and 32-bit integer WAV formats correctly
* Display correct offset value in Results tab
* Added silence trimming option (on by default)
* Added scale display and other enhancements in the spectrogram windows, including annotation support
* Right-click now removes the last annotation added to the chart
* Changed the waveform Y axis to display in dB rather than 1 to -1 floating point by default
* Added option to switch between dB and floating point view of Y axis
* Fixed the 100% that's really a 'nearly 100%' display
* Fixed the installer so previous versions are removed from the list of installed packages
* Handled different number of samples in left and right channels when working on L+R mono mix-down channel
* Added an optional, more stable drift correction method if the normal method does not converge
* Various minor spelling/terminology fixes

## Changes in 1.0.18b
* Added Stereo XY difference test to the Comparator
* Added Preference XY different test to the Comparator
* Added file and settings information to the test result window for validation
* Changed the behavior of play buttons and menu items, including the comparator to not require a Show or Match button press
* Extended default frequency scale on plots to Nyquist frequency
  
## Changes in 1.0.17b
* Fixed a problem with the Index out of Bounds error when engaging DC offset removal option
* Fixed a problem that resulted in Reference level being adjusted to match Comparison, instead of the other way around
* Added support for down-mixing stereo files into a mono track for comparison (DSD not supported with L+R yet)
* Fixed a small glitch with FFT windowing routine that resulted in a low frequency spurious tone with certain window types
* Added track RMS and peak values before and after matching to the Results tab
* Added drag-and-drop of individual files to the Reference and Comparison boxes

## Changes in 1.0.15b
* Fixed a problem that caused larger phase difference in the first few second of the track compared to the rest of the track
* Removed non-linear polynomial gain correction
* Removed non-linear drift correction
* Added non-linear EQ/frequency matching correction

## Changes in 1.0.14b
* Added manual and automatic resampling for audio playback on audio cards where native rates are not supported
* Changed non-linear drift correction to be off by default

## Changes in 1.0.12b
* Fix for audio driver shown in the list but audio not playing
* Fix for DSD file right channel selector causing an error
* Set minimum limits on plots to avoid zooming in to the rounding error in floating point computations

## Changes in 1.0.11b
* One more attempt at supporting high-DPI in Windows 10
* Added font selector for custom font face and size
* Changed frequency label routine to show more decimal places to eliminate duplicate-looking labels

## Changes in 1.0.10b
* Hopefully better control positioning and sizing under diffrent Windows DPI settings and versions
* Slightly faster DSD reader
* More low-pass filter settings, including 'none' for DSD conversion

## Changes in version 1.0.9b
* Fixed setting correct audio driver after restart
* Changed driver list to display Friendly Name
* Changed DSD conversion process from CIC demodulator to a low-pass FIR filter, added DSD conversion settings
* Improved Log axis label formatting
* Added support for drag-and-drop of one or two audio files into DW main window from Windows Explorer
* Added a swap option to File menu

## Changes in version 1.0.8b
* Fixed volume control during playback
* Fixed driver selection for WASAPI drivers
* Added Log frequency axis display option


## Changes in version 1.0.7b
* Added high-contrast plot display option
* Reversed the direction of the plot in Delta of Spectra, so that it is now Comparison - Reference
* Added tooltips to controls on the main screen, settings , and Comparator screens
* Fixed the plot refresh button as it caused certain parts of the plots to be hidden

## Changes in version 1.0.6b
* Improved plot axis labeling with a more intelligent choice of units and decimal places to display
* Added AB/X style Comparator
* Added the support for DFF-formated DSD files (uncompressed only) 
* Added playback position display and ability to set playback position by clicking on the control
* Added the option to turn off MD5 hash in the results, as this could cause some delay when processing large files
* Changed how the Trim functions work: the data that is trimmed is now skipped when reading the file. Previously the whole file was loaded into memory and then trimmed
* Added a 50% bit-perfect match result. This is how many bits the files need to be reduced to in order for 50% of the samples to match exactly.
* Added support for two filters. A low-pass and a high-pass filter can now be applied simultaneously

## Changes in version 1.0.5b

* Added logging for problem reporting and troubleshooting. Available under Help->Logging Menu
* Added A-Weighted measurements to better represent audible differences, shown as dBA value in RMS Difference and Correlated-Null values. This applies greater weight to frequencies that the human ear is sensitive to.
* Fixed linear drift correction. Should work much better than in the previous version (turn off NonLinear Drift correction setting)
* Improved clock drift calculation, works more consistently and accurately
* Added tab display selection in settings. You can now chose what tabs and charts will be available after a Match. This also controls what plots will be included in a report: any plot that is not visible will not be included.
* Added a Plot showing Delta of Spectra -- this is the spectrum of Comparison file subtracted from the spectrum of Reference. The closer this is to a flat line at zero, the better the spectra match between two files.
* Improved, formatted display of the results on the status bar
* File menu now has two additional options 
  * Save Compare File
  * Save Delta File
  


___
{% include links.html %}
