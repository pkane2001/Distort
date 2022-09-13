---
title: Multitone - Loopback Analyzer for Audio
tags: [Multitone]
keywords: release notes, announcements, what's new, new features
last_updated: August 17, 2022
summary: "Multitone is currently in beta test. Use at your own risk!"
sidebar: mydoc_sidebar
permalink: multitone-exp.html
folder: mydoc
comments: true
---
<div>
<h1>Multitone Variable Expression support</h1><br>
<h2 id="op-variables">Supported variables</h2>

Variables can be inserted into any expression at any point by enclosing them in { } characters

<br>Example 1:<br><code><strong>Sample Rate is <u>{recordSampleRate}</u> Hz</strong></code> <br>
<br>Example 2:<br><code><strong>Sample Rate is <u>{recordSampleRate}</u> Hz and <u>{playSampleRate}</u> Hz</strong></code>

Multiple variables can be inserted into the same result. If two channel measurements are made, all variables can be used with number 2 added at the end to refer to the same variable results in the second channel.

<br>Example:<br><code><strong>THD in {channel2} is {thd2}dB</strong></code> <br>

Calculations can be used combining multiple variables (see Supported Operators and Math functions below).

<br>Example:<br><code><strong>THD % in {channel} is {(10^(thd/20))*100:}%</strong></code> <br>

Formatting can be applied to displayed variables. Numeric variables are displayed, by default, with all whole digits, and one decimal fraction. To add additional decimal points, use a format of this form:   {thd:0.0000000} for example. To display the number in scientific notation, use {tdn:G}. Many other formatting options are available.

Here's the list of variables available for display or to be used in a calculation. All numeric variables that can be, are expressed in dB. You can convert them to other desired units by adding a calcluation.

<br>


<figure class="wp-block-table"><table><tbody><tr><th>Variable</th><th>Description</th></tr><tr><td><strong>level</strong></td><td><code>Peak level of the recorded signal (dB)</code></td></tr>

<tr><td><strong>levelRMS</strong></td><td><code>RMS level of the recorded signal (dB)</code></td></tr>
<tr><td><strong>gain</strong></td><td><code>Play Gain setting during recording (dB)</code></td></tr>
<tr><td><strong>tdn</strong></td><td><code>Measured TD+N total distortion + noise(dB)</code></td></tr>
<tr><td><strong>thd</strong></td><td><code>Measured THD total harmonic distortion (dB)</code></td></tr>
<tr><td><strong>imd</strong></td><td><code>Measured IMD intermodulation distortion (dB)</code></td></tr>

<tr><td><strong>snr</strong></td><td><code>Mesaured SNR signal-to-noise ratio (dB)</code></td></tr>
<tr><td><strong>noise</strong></td><td><code>Measured noise level (dB)</code></td></tr>
<tr><td><strong>sfdr</strong></td><td><code>Measured SFDR spurious free dynamic range (dB)</code></td></tr>
<tr><td><strong>sfdrFreq</strong></td><td><code>Frequency where SFDR was measured (Hz)</code></td></tr>
<tr><td><strong>enob</strong></td><td><code>Measured ENOB effective number of bits</code></td></tr>


<tr><td><strong>freqH1</strong></td><td><code>Frequency of the fundamental component (Hz)</code></td></tr>
<tr><td><strong>amplH1</strong></td><td><code>Amplitude of the fundamental component (dB)</code></td></tr>
<tr><td><strong>testSignal</strong></td><td><code>Name of the test signal used to measure (text)</code></td></tr>

<tr><td><strong>fftSize</strong></td><td><code>FFT size used for analysis</code></td></tr>
<tr><td><strong>window</strong></td><td><code>FFT window used for analysis (text)</code></td></tr>


<tr><td><strong>fromFreq</strong></td><td><code>Lowest measured frequency (Hz)</code></td></tr>
<tr><td><strong>toFreq</strong></td><td><code>Highest measured frequency (Hz)</code></td></tr>
<tr><td><strong>averages</strong></td><td><code>Number of averages collected</code></td></tr>
<tr><td><strong>overlap</strong></td><td><code>Average Overlap (%)</code></td></tr>

<tr><td><strong>playSampleRate</strong></td><td><code>Output sample rate (Hz)</code></td></tr><tr><td><strong>recordSampleRate</strong></td><td><code>Input sample rate (Hz)</code></td></tr><tr><td><strong>ResultLabel</strong></td><td><code>Text label assigned to this measurement in history</code></td></tr>

<tr><td><strong>channel</strong></td><td><code>Channel label used for this result (text)</code></td></tr>
<tr><td><strong>channelNumber</strong></td><td><code>Channel 0 or 1 used for this result</code></td></tr>


<tr><td><strong>channelsIn</strong></td><td><code>Channels selector for ADC</code></td></tr>
<tr><td><strong>channelsOut</strong></td><td><code>Channels selector for DAC</code></td></tr>
<tr><td><strong>driverIn</strong></td><td><code>Audio driver used for input</code></td></tr>
<tr><td><strong>driverOut</strong></td><td><code>Audio driver used for output</code></td></tr>
<tr><td><strong>resultTitle</strong></td><td><code>FFT size used for analysis</code></td></tr>





</tbody></table></figure>


<br><br>


<h2 id="op-constants-funcs">Supported operators, constants and functions</h2>



<h3>Supported Operators</h3>



<figure class="wp-block-table"><table><tbody><tr><th>Operator</th><th>Description</th></tr><tr><td>+</td><td>Additive operator / Unary plus / Concatenate string / Datetime addition</td></tr><tr><td>&amp;</td><td>Concatenate string</td></tr><tr><td>–</td><td>Subtraction operator / Unary minus / Datetime subtraction</td></tr><tr><td>*</td><td>Multiplication operator, can be omitted in front of an open bracket</td></tr><tr><td>/</td><td>Division operator</td></tr><tr><td>%</td><td>Remainder operator (Modulo)</td></tr><tr><td>^</td><td>Power operator</td></tr></tbody></table></figure>



<h3>Supported conditional statements</h3>



<figure class="wp-block-table"><table><tbody><tr><th>Conditional statement</th><th>Description</th></tr><tr><td><strong>IF</strong>(logical_condition, value_if_true, value_if_false)</td><td>Example:<br><code><strong>IF(2&gt;1,"Pass","Fail")</strong></code></td></tr><tr><td><strong>SWITCH</strong>(expression, val1,result1, [val2,result2], …, [default])</td><td>Example:<br><strong><code>SWITCH(3+2,5,"Apple",7,"Mango",3,"Good","N/A")</code></strong></td></tr></tbody></table></figure>



<h3>Supported logical and math functions</h3>



<figure class="wp-block-table"><table><tbody><tr><th>Function<sup>*</sup></th><th>Description</th></tr><tr><td><strong>AND</strong>(logical1, [logical2], …)</td><td>Determine if all conditions are TRUE</td></tr><tr><td><strong>OR</strong>(logical1, [logical2], …)</td><td>Determine if any conditions in a test are TRUE</td></tr><tr><td><strong>NOT</strong>(<em>logical</em>)</td><td>To confirm one value is not equal to another</td></tr><tr><td><strong>XOR</strong>(logical1, [logical2], …)</td><td>Exclusive OR function</td></tr><tr><td><strong>SUM</strong>(number1, [number2],…)</td><td>Return sum of numbers supplied</td></tr><tr><td><strong>AVERAGE</strong>(number1, [number2],…)</td><td>Return average of numbers supplied</td></tr><tr><td><strong>MIN</strong>(number1, [number2],…)</td><td>Return&nbsp;the smallest value from the numbers supplied</td></tr><tr><td><strong>MAX</strong>(number1, [number2],…)</td><td>Return&nbsp;the biggest value from the numbers supplied</td></tr><tr><td><strong>MOD</strong>(number, divisor)</td><td>Get remainder of two given numbers after division operator.</td></tr><tr><td><strong>ROUND</strong>(number, num_digits)</td><td>Returns the rounded approximation of given number using half-even rounding mode<br>( you can change to another rounding mode)</td></tr><tr><td><strong>FLOOR</strong>(number, significance)</td><td>Rounds a given number towards zero to the nearest multiple of a specified significance</td></tr><tr><td><strong><code>CEILING</code></strong>(number, significance)</td><td>Rounds a given number away from zero, to the nearest multiple of a given number</td></tr><tr><td><strong>POWER</strong>(number, power)</td><td>Returns the result of a number raised to a given power</td></tr><tr><td><strong>RAND</strong>()</td><td>Produces a random number between 0 and 1</td></tr><tr><td><strong>SIN</strong>(number)</td><td>Returns the trigonometric sine of the angle given in radians</td></tr><tr><td><strong>SINH</strong>(number)</td><td>Returns the hyperbolic sine of a number</td></tr><tr><td><strong>ASIN</strong>(number)</td><td>Returns the arc sine of an angle, in the range of -pi/2 through pi/2</td></tr><tr><td><strong>COS</strong>(number)</td><td>Returns the trigonometric cos of the angle given in radians</td></tr><tr><td><strong>COSH</strong>(number)</td><td>Returns the hyperbolic cos of a number</td></tr><tr><td><strong>ACOS</strong>(number)</td><td>Returns the arc cosine of an angle, in the range of 0.0 through pi</td></tr><tr><td><strong>TAN</strong>(number)</td><td>Returns the tangent of the angle given in radians</td></tr><tr><td><strong>TANH</strong>(number)</td><td>Returns the hyperbolic tangent of a number</td></tr><tr><td><strong>ATAN</strong>(number)</td><td>Returns the arc tangent of an angle given in radians</td></tr><tr><td><strong>ATAN2</strong>(x_number, y_number)</td><td>Returns the arctangent from x- and y-coordinates</td></tr><tr><td><strong>COT</strong>(number)</td><td>Returns the cotangent of an angle given in radians.</td></tr><tr><td><strong>COTH</strong>(number)</td><td>Returns the hyperbolic cotangent of a number</td></tr><tr><td><strong>SQRT</strong>(number)</td><td>Returns the correctly rounded positive square root of given number</td></tr><tr><td><strong>LN</strong>(number)</td><td>Returns the natural logarithm (base&nbsp;<em>e</em>) of given number</td></tr><tr><td><strong>LOG10</strong>(number)</td><td>Returns the logarithm (base 10) of given number</td></tr><tr><td><strong>EXP</strong>(number)</td><td>Returns e raised to the power of given number</td></tr><tr><td><strong>ABS</strong>(number)</td><td>Returns the absolute value of given number</td></tr><tr><td><strong>FACT</strong>(number)</td><td>Returns the factorial of a given number</td></tr><tr><td><strong>SEC</strong>(number)</td><td>Returns the secant of an angle given in radians</td></tr><tr><td><strong>CSC</strong>(number)</td><td>Returns the cosecant of an angle given in radians</td></tr><tr><td><strong>PI</strong>()</td><td>Return value of Pi</td></tr><tr><td><strong>RADIANS</strong>(degrees)</td><td>Convert degrees to radians</td></tr><tr><td><strong><code>DEGREES</code></strong><code>(radians)</code></td><td>Convert radians to degrees</td></tr><tr><td><strong>INT</strong>(number)</td><td>Returns the Integer value of given number</td></tr></tbody></table></figure>



<h3>Supported Constants</h3>



<figure class="wp-block-table"><table><tbody><tr><th>Constant</th><th>Description</th></tr><tr><td>e</td><td>The value of&nbsp;<em>e</em></td></tr><tr><td>PI</td><td>The value of&nbsp;<em>PI</em></td></tr><tr><td>TRUE</td><td>The boolean true value</td></tr><tr><td>FALSE</td><td>The boolean false value</td></tr><tr><td>NULL</td><td>The null value</td></tr></tbody></table></figure>



<h3>Supported text functions</h3>



<figure class="wp-block-table"><table><tbody><tr><th>Function</th><th>Description</th></tr><tr><td><strong>LEFT</strong>(text, num_chars)</td><td>Extracts a given number of characters from the left side of a supplied&nbsp;<strong>text string</strong></td></tr><tr><td><strong>RIGHT</strong>(text, num_chars)</td><td>Extracts a given number of characters from the right side of a supplied&nbsp;<strong>text string</strong></td></tr><tr><td><strong>MID</strong>(text, start_num, num_chars)</td><td>Extracts a given number of characters from the middle of a supplied&nbsp;<em>text string</em></td></tr><tr><td><strong>REVERSE</strong>(text)</td><td>Reverse a string</td></tr><tr><td><strong>ISNUMBER</strong>(text)</td><td>Check if a value is a number</td></tr><tr><td><strong>LOWER</strong>(text)</td><td>Converts all letters in the specified string to lowercase</td></tr><tr><td><strong>UPPER</strong>(text)</td><td>Converts all letters in the specified string to uppercase</td></tr><tr><td><strong>PROPER</strong>(text)</td><td>Capitalizes words given text string</td></tr><tr><td><strong>TRIM</strong>(text)</td><td>Removes extra spaces from text</td></tr><tr><td><strong>LEN</strong>(text)</td><td>Returns the length of a&nbsp;<strong>string</strong>/&nbsp;<strong>text</strong></td></tr><tr><td><strong>TEXT</strong>(value, [format_text])</td><td>Convert a numeric value into a text string. You can use the TEXT function to embed formatted numbers inside text<br>Example:<br><code><strong><div class="enlighter-default enlighter-v-inline enlighter-t-enlighter "><span class="enlighter"><span class="enlighter-m0">TEXT</span><span class="enlighter-g1">(</span><span class="enlighter-n1">123</span><span class="enlighter-g1">)</span><span class="enlighter-text"> -</span><span class="enlighter-g1">&gt;</span><span class="enlighter-text"> </span><span class="enlighter-n1">123</span></span></div><code data-enlighter-language="generic" class="EnlighterJSRAW enlighter-origin">TEXT(123) -&gt; 123</code><br><div class="enlighter-default enlighter-v-inline enlighter-t-enlighter "><span class="enlighter"><span class="enlighter-m0">TEXT</span><span class="enlighter-g1">(</span><span class="enlighter-m0">DATEVALUE</span><span class="enlighter-g1">(</span><span class="enlighter-s0">"2021-01-23"</span><span class="enlighter-g1">)</span><span class="enlighter-text">,</span><span class="enlighter-s0">"dd-MM-yyyy"</span><span class="enlighter-g1">)</span><span class="enlighter-text"> -</span><span class="enlighter-g1">&gt;</span><span class="enlighter-text"> </span><span class="enlighter-n1">23</span><span class="enlighter-text">-</span><span class="enlighter-n4">01</span><span class="enlighter-text">-</span><span class="enlighter-n1">2021</span></span></div><code data-enlighter-language="generic" class="EnlighterJSRAW enlighter-origin">TEXT(DATEVALUE("2021-01-23"),"dd-MM-yyyy") -&gt; 23-01-2021</code><br><div class="enlighter-default enlighter-v-inline enlighter-t-enlighter "><span class="enlighter"><span class="enlighter-m0">TEXT</span><span class="enlighter-g1">(</span><span class="enlighter-n0">2.61</span><span class="enlighter-text">,</span><span class="enlighter-s0">"hh:mm"</span><span class="enlighter-g1">)</span><span class="enlighter-text"> -</span><span class="enlighter-g1">&gt;</span><span class="enlighter-text"> </span><span class="enlighter-n1">14</span><span class="enlighter-text">:</span><span class="enlighter-n1">38</span></span></div><code data-enlighter-language="generic" class="EnlighterJSRAW enlighter-origin">TEXT(2.61,"hh:mm") -&gt; 14:38</code><br><div class="enlighter-default enlighter-v-inline enlighter-t-enlighter "><span class="enlighter"><span class="enlighter-m0">TEXT</span><span class="enlighter-g1">(</span><span class="enlighter-n0">2.61</span><span class="enlighter-text">,</span><span class="enlighter-s0">"[hh]"</span><span class="enlighter-g1">)</span><span class="enlighter-text"> -</span><span class="enlighter-g1">&gt;</span><span class="enlighter-text"> </span><span class="enlighter-n1">62</span></span></div><code data-enlighter-language="generic" class="EnlighterJSRAW enlighter-origin">TEXT(2.61,"[hh]") -&gt; 62</code><br><div class="enlighter-default enlighter-v-inline enlighter-t-enlighter "><span class="enlighter"><span class="enlighter-m0">TEXT</span><span class="enlighter-g1">(</span><span class="enlighter-n0">2.61</span><span class="enlighter-text">,</span><span class="enlighter-s0">"hh-mm-ss"</span><span class="enlighter-g1">)</span><span class="enlighter-text"> -</span><span class="enlighter-g1">&gt;</span><span class="enlighter-text"> </span><span class="enlighter-n1">14</span><span class="enlighter-text">-</span><span class="enlighter-n1">38</span><span class="enlighter-text">-</span><span class="enlighter-n1">24</span></span></div><code data-enlighter-language="generic" class="EnlighterJSRAW enlighter-origin">TEXT(2.61,"hh-mm-ss") -&gt; 14-38-24</code><br><div class="enlighter-default enlighter-v-inline enlighter-t-enlighter "><span class="enlighter"><span class="enlighter-m0">TEXT</span><span class="enlighter-g1">(</span><span class="enlighter-m0">DATEVALUE</span><span class="enlighter-g1">(</span><span class="enlighter-s0">"2021-01-03"</span><span class="enlighter-g1">)</span><span class="enlighter-text">-</span><span class="enlighter-m0">DATEVALUE</span><span class="enlighter-g1">(</span><span class="enlighter-s0">"2021-01-01"</span><span class="enlighter-g1">)</span><span class="enlighter-text">,</span><span class="enlighter-s0">"[h]"</span><span class="enlighter-g1">)</span><span class="enlighter-text"> -</span><span class="enlighter-g1">&gt;</span><span class="enlighter-text"> </span><span class="enlighter-n1">48</span></span></div><code data-enlighter-language="generic" class="EnlighterJSRAW enlighter-origin">TEXT(DATEVALUE("2021-01-03")-DATEVALUE("2021-01-01"),"[h]") -&gt; 48</code><br><div class="enlighter-default enlighter-v-inline enlighter-t-enlighter "><span class="enlighter"><span class="enlighter-m0">TEXT</span><span class="enlighter-g1">(</span><span class="enlighter-m0">TIME</span><span class="enlighter-g1">(</span><span class="enlighter-n1">12</span><span class="enlighter-text">,</span><span class="enlighter-n4">00</span><span class="enlighter-text">,</span><span class="enlighter-n4">00</span><span class="enlighter-g1">)</span><span class="enlighter-text">-</span><span class="enlighter-m0">TIME</span><span class="enlighter-g1">(</span><span class="enlighter-n1">10</span><span class="enlighter-text">,</span><span class="enlighter-n1">30</span><span class="enlighter-text">,</span><span class="enlighter-n1">10</span><span class="enlighter-g1">)</span><span class="enlighter-text">,</span><span class="enlighter-s0">"hh hours and mm minutes and ss seconds"</span><span class="enlighter-g1">)</span><span class="enlighter-text"> -</span><span class="enlighter-g1">&gt;</span><span class="enlighter-text"> </span><span class="enlighter-s0">"01 hours and 29 minutes and 50 seconds"</span></span></div><code data-enlighter-language="generic" class="EnlighterJSRAW enlighter-origin">TEXT(TIME(12,00,00)-TIME(10,30,10),"hh hours and mm minutes and ss seconds") -&gt; "01 hours and 29 minutes and 50 seconds"</code></strong></code></td></tr><tr><td><strong>REPLACE</strong>(old_text, start_num, num_chars, new_text)</td><td>Replaces characters specified by location in a given text string with another text string</td></tr><tr><td><strong>SUBSTITUTE</strong>(text, old_text, new_text)</td><td>Replaces a set of characters with another</td></tr><tr><td><strong>FIND</strong>(find_text, within_text, [start_num])</td><td>Returns the location of a substring in a string (case sensitive)</td></tr><tr><td><strong>SEARCH</strong>(find_text, within_text, [start_num])</td><td>Returns the location of a substring in a string (case insensitive)</td></tr><tr><td><strong>CONCAT</strong>(text1, text2, text3,…)</td><td>Combines the text from multiple strings</td></tr><tr><td><strong>ISBLANK</strong>(text)</td><td>Returns TRUE when a given string is null or empty, otherwise return FALSE</td></tr><tr><td><strong>REPT</strong>(text, repeat_time)</td><td>Repeats characters a given number of times</td></tr><tr><td><strong>CHAR</strong>(char_code)</td><td>Return character from ascii code</td></tr><tr><td><strong>CODE</strong>(char)</td><td>Returns a ascii code of a character</td></tr><tr><td><strong>VALUE</strong>(text)</td><td>Convert numbers stored as text to numbers</td></tr></tbody></table></figure>

</div>

___
{% include links.html %}
