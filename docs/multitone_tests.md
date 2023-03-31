---
title: Multitone - Loopback Analyzer for Audio
tags: [Multitone]
keywords: test plan configuration and execution
last_updated: March 27, 2023
summary: "Multitone is currently in beta test. Use at your own risk!"
sidebar: mydoc_sidebar
permalink: multitone_tests.html
folder: mydoc
toc: true
comments: true
---

## Multitone Test Plans
A new feature added in Multitone v1.0.76 and later is the Test Plan set up and execution. The feature is designed for performing repeatable, highly structured set of tests on a component using all the Multitone features and measurement capabilities.

A test plan is a single file that defines multiple measurements to be performed in sequence. Each measurement is completely pre-configured when the plan is created. The only variable left to select is the input and output devices: these need to be selected prior to the test execution.

These are main operations one can perform with a test plan:

* Create a new test plan
* Open or import an existing or downloaded test plan
* Modify an existing test plan
* Execute a test plan

All the Test Plan functions are available through the Test menu in Multitone. While the test plan is executing, at completion of each measurement step, Multitone will record one or more images of the plots that are generated as the result of the measurement. The images to record are configured in the Plot to Capture setting for each step. To capture more than one plot, separate the names of the plots by commas, for example: *Freq Response,Phase,Impulse*. The image file names will contain the name of the step, as well as, the plot that was captured.


## Creating a new test plan
From Test->Test Plan menu select (Add New...) option. This will bring up the Test Plan editor with a new, blank test plan:

![multitone1](images/newtestplan.png)

To create a complete test plan, add one or more measurement steps in the left box, and change the configuration/settings for each step on the right by selecting that step, first.
Two ways to create a new measurement step are to use an existing Multitone Preset as the base configuration (pick one of the presets from the Add a Preset drop-down list) or to click the Add New button. The Add New button is perhaps the simplest way to add a new measurement step, as it simply copies all the existing configuration from the main window in Multitone. The way to use these two methods differ in details:

* Using a preset, select the desired one from the list. Then, modify all the settings in the property panel to the right. To add more steps, simply pick the same (or different) preset from the list, and modify it as necessary in the propertly sheet.

* Using Add New button, first go to the main Multitone Window. Configure and run any desired test, make sure the results look correct and all the settings are properly configured. Then, go to the desired test plan and click Add New button. The new measurement step will be a complete copy of the measurement you just performed in main Multitone window. You can still go ahead and modify any properties or settings for this measurement, but it should be 99% fully configured by the time you click 'Add New'. Repeat the same steps for adding other measurements.

## Editing a test plan
From the test plan execution window, you can chose any of the previously created plans, and then modify them by clicking the 'Edit Plan' button:

![multitone1](images/edittestplan1.png)

You will see the list of all the measurement steps already defined for this test plan on the left. Click on any of the steps in the list to bring up all settings related to that step. Modify any of the settings on the right. When finished changing, press Save button, or Save As... to save as a new plan. You can change the name of each step at the top right.

* To re-arrange measurement steps, drag and drop any of the steps in the list
* To delete a measurement step, select it in the list, then click the red 'X' button below
* To add a new measurement step, select a preset or press Add New button, as before
* 




___
{% include links.html %}
