Issues/enhancements

1.0.31 - July 30-31, 2022
* DONE Sweep window auto-scaling and min/max range in X axis (+/-1 db extra) and Y axis (-120db limit)
* DONE (PK) Fix sweep X-axis labels to show decimals when zooming in
* Additional Logging for troubleshooting Issues
* MAYBE??? Empty spectrum screen and NaNdB display for THD+N with AP 32 Multitone signal (@Blumline 88). Any sample rate ratio of greater than 1:2 causes this (greater than 96k on slower laptop)
* Bug crash with System.Null reference in Oxyplot when changing different color in History (MC_RME)
* Enhancements (MC_RME)
in History:
    - please add a dedicated Label column. I would like to keep the time information.
    - using Enter to jump to the next entry for editing and so on is very quick, but doesn't work for the lowest (last) entry

   [DONE] - Wish: now that filter response curves can be saved quickly and perfectly measured, please add the option to show a vertical line at 22.05 and alternatively 24 kHz, in the spectrum and FR view. That saves us to add this one later with external graphics tools, improves overview directly in the measurement, and allows to do the famous Reis measurement with just two measurements using History.

    [DONE] - The 'low contrast' mode option seems more like a dark/bright theme choice. Plots then come out as I want them, with white background. Unfortunately the colors used seem not optimal, like in the below screenshot. That text color is ok for black background, but hard to read for white.
    
    [DONE] I would prefer to have the same white background also in the program, instead of the quite boring grey, which reduces readability for me.

    [DONE] - The export plots - and that can be nicely seen in your own exports pasted here (https://www.audiosciencereview.com/...loopback-analyzer-software.27844/post-1265319) - typically suffer from unreadable scales (online, but especially when printed in a pdf). The workaround is to make the plot more small, so the scale text size gets bigger in proportion (see below). But to do so the program window be must made smaller horizontally and vertically so that all elements in it get crushed and overlap. The surface becomes unusable.
    
   ALREADY DONE -- A solution could be to allow Clipboard image scale to accept values below 1 - like 0.5 and 0.25. That is currently not in the allowed range.

    - That text line is really not optimally placed (and not visible in the program itself). I had to intentionally shift the Y scale so that it doesn't collide with the measurement. Also the Multitone label is most probably better placed in the upper right for most measurements. 
    
    Now that Multitone reached that level I dare to ask for another one. It would be nice to be able to edit the top line (Spectrum (dBr)), turning it into a full description of the measurement (here: ADI-2 Pro FS R BE DAC filter responses @ 44.1 kHz).

* Sweep cycle starts at 0/60 instead of 1/60 (Rantapossu)
* (bennetng) 
  - @pkane these issues bothered me for a long time, but I need to set the min freq in both the main and setting windows to reliably limit the displayed frequencies. Also, if I toggle the "Frequency log scale" box, the frequency limit will not work as expected again. If I click "Reset Axes" the plot will also scaled to another (undesired) range.

  - Also, if I set "Average" to more than 256, regeardless of FFT size, the averaging count (red text) during test will often stop to increase at somewhere between 300-400 and the FFT plot will also stop to update, and displaying an unfinished plot as the final result.

* DONE (Sokel) - Averages overlap is missing decimal separator when set through settings
