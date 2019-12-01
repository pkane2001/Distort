---
title: Reports 
tags: [report]
keywords: report, plot, chart
last_updated: February 7, 2019
summary: "DeltaWave is the initial beta release of this software. Use at your own risk!"
sidebar: mydoc_sidebar
permalink: reports.html
folder: mydoc
toc: true
datatable: true
comments: true
---

DeltaWave can generate a detailed report in HTML format from the results of any two file comparison. Once the comparison is completed, the report can be created by selecting File->Generate Report... menu.

To create multiple reports from a list of files, please use File->Report Cruncher...

## Single Report

When File->Generate Report menu is invoked, it will create an HTML page that combines a table of results, as well as multiple charts from the analysis. Analysis must be performed first, before creating a report, otherwise the report will not have any content.

The report generator will ask for a name of the HTML file to generate, and will then commence to create the report. 

When completed, the report will be opened in the default browser configured in your system. Please note that a modern browser is required to view this report, some older browsers, such as Internet Explorer, may not be able to fully render all the embedded images.

## Manual control

Press the <img src="images/img7.png" style="vertical-align: middle" /> button. You'll see a Zoom dialog where you can enter the desired coordinates in X and Y axis, independently:

<img src="images/img8.png" style="vertical-align: middle" />

Press *Apply* button to see the effect of the changes you made without exiting the Zoom dialog.

## Zooming in and out with the mouse

Zoom can be controlled by using the mouse scroll wheel. To zoom in on a specific point in the chart using both axis, position the mouse cursor at the desired point, and then turn the scroll wheel towards you. To zoom out, simple move the wheel in the opposite direction.

If you want to zoom in only on one axis (for example zoom-in only on the amplitude, but not the frequency), position the mouse outside the plot area, over the axis label that you'd like to zoom-in on, and then turn the scroll wheel towards you. To zoom-out, move the wheel in the opposite direction.

## Moving the plot around using the mouse

To reposition the plot to a different starting/ending coordinates, move the cursor to anywhere in the plot area and then press the left button down and drag the plot in the desired direction. This allows for motion in both axis.

If you want to reposition just one of the axis, X or Y, you can position the cursor over any of the labels on that axis, and move it while pressing down the left mouse button.

## Complete redo of the plots

If the charts are hard to get to the original state, the simplest thing to do without re-running the whole *Match* operation is to press the redo button: <img src="images/img10.png" style="vertical-align: middle" />. This redraws all the plots, updating all the data without doing any of the recomputation. You may still want to press the Reset Axis button if the zoom level is not restored to the desired state.

___
{% include links.html %}
