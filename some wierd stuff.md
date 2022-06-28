<div>
   <a href="https://indy.ctf.eng.run/challenge/14"><img src="https://img.shields.io/badge/some wierd stuff: %20-Click%20to%20Solve-green[700]" height="25"></a>
   
  <img src="https://img.shields.io/badge/Points%3A-260-red" align="right" height="25">
     <img src="https://img.shields.io/badge/Category%3A%20-Wireless-orange" align="right" height="25">
</div>

<div align="center">
    <h1>some wierd stuff</h1>
</div>

### Approach:

- I used <a href="https://github.com/miek/inspectrum">inspectrum</a> for this challenge. Opening the file as provided just shows the plot as all red. Reading the github README indicates we need to change the file extension to .cu8. However, I tried this, and the plot looked wrong in a different way:

<div align="center" >
<img width="600" src="https://user-images.githubusercontent.com/91147942/176124450-a5609002-e1d4-4dd8-b1fa-7a8d095a64b7.png">
</div>

- Inspectrum shows a horizontal "waterfall plot" with time along the X axis, frequency along the Y axis, and signal strength based on color (warmer colors = stronger signal). The "hot" part of the signal was split between the very top and very bottom frequencies, when they should be joined somewhere in the middle. During the competition I tried changing the file extension to .cs8 and .u8, and .u8 looked the best (after making sure to adjust the sliders under the "Spectogram" section), so I just assumed that I was wrong and the file only provided 1 data point per sample instead of 2 (i.e. just the real value instead of the complex value). However, in the GRC flowchart I made after the competition there are 2 pipelines for the file, 1 for real samples and 1 for complex samples. Only the one assuming complex samples produces clean output, so I think this is actually a bug with inspectrum and I'm right about the samples being complex. Regardless, if you change the extension to .u8, open in inspectrum, scroll the file and play with the sliders, you should eventually find a section which looks like this:

<div align="center">
<img width="600" src="https://user-images.githubusercontent.com/91147942/176125077-fcec5903-4f37-48b8-92a4-9e16ada18598.png">
</div>

- This bright area is the transmission we need to decode! Ideally it would show up as a horizontal dashed line, where dashes represent 1s and gaps represent 0s. However, the signal doesn't show up clearly in the frequency domain (and a waterfall plot is just a frequency plot over time). Thankfully, inspectrum provides some features to convert the output to a time domain plot where the signal appears more clearly! Right click -> Add derived plot -> Add amplitude plot. Use your mouse to center the thin red line on the hottest part of the waterfall plot and drag the white sidebars all the way to the top/bottom (advanced readers: these bars serve as an interactive bandpass filter!). The X axis of this new plot is time and the Y axis is overall signal strength (amplitude, or magnitude of the complex signal). At this point you should be able to see some flat-topped peaks (hard to see since they are covered up by the border between the derived plot and the waterfall plot) and noisy troughs in the derived plot, which are the 1s and 0s for this transmission! The derived plot will be slightly offset from the waterfall plot but that's just a quirk of inspectrum.

<div align="center">
<img width="600" src="https://user-images.githubusercontent.com/91147942/176125457-f0111cf6-8f2b-4909-913c-90c11f96fe76.png">
</div>

- To make it easier to count the binary data, you can check the "Enable cursors" checkbox, change the number of symbols to 37 (since that is the number of bits in this transmission) and drag the left and right limits until the time periods roughly match the transitions in the derived plot as shown below:

<div align="center">
<img width="600" src="https://user-images.githubusercontent.com/91147942/176126058-fb600510-6743-4ff0-a6ff-b9272c07837d.png">
</div>

- At this point you can simply read out the flag bits:

<div align="center">
<img width="600" src="https://user-images.githubusercontent.com/91147942/176126546-9713c8df-c403-4910-af30-e34d7eaf09fc.png">
</div>

### Flag:

`ictf{1011001011011001011001001001001011001}`
