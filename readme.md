# UWA Energy Scavenger
 Creates the basic functionality of an [oscilloscope](https://en.wikipedia.org/wiki/Oscilloscope) ( plus [spectrum analyser](https://en.wikipedia.org/wiki/Spectrum_analyzer) Spectrum Analyser and Cross-correlation scope) from a very low cost [Arduino](https://www.arduino.cc/) to allow the ability to explore signals, collect data and complete high-school/University laboratories even when students are completing portions of their studies remotely.
 ## QuickStart
  Follow these steps to get up and running with with Adri/Ardu-Scope quickly:
  * Select the Green CODE button (top right) and download ZIP.  Once downloaded, unzip the files to a folder.   
  * Upload the [AdriArduScope.ino](AdriArduScope/AdriArduScope.ino) file to your Arduino.  Use your favorite upload tool, most likely the [Arudino IDE](https://www.arduino.cc/en/software).  Select the correct type of Arduino you have before uploading - this has been tested on a Nano, Uno and Mega.  Also note the serial (COM) port you are using to access the Arduino.  You may need this later.  
  * Close the Arduino IDE/Serial Monitor and with the Arduino plugged in, run [AdriArduScope.py](AdriArduScope.py) under python 3 - the python code  requires matplotlib, numpy and pyserial. At this time, executables for Windows and MACs have not been produced but may be in the future.  Install the appropriate versions of these either conda or pip managed dependencies:
    * [Install matplotlib here](https://matplotlib.org/stable/users/installing.html)
    *[Install numpy here](https://numpy.org/install/)
    * And either the [pip version of pyserial](https://pypi.org/project/pyserial/) or the [conda version of pyserial](https://anaconda.org/anaconda/pyserial)  

  * If the Adri/Ardu-Scope is the only device connected to the COM/ACM port, then it should find it and start right away.  If you have more than 1 device on the COM/ACM port, then a list will appear in the python console and you need to select the correct port to start the Adri/Ardu-Scope.  Use the same port as identified when you uploaded the code via the [Arudino IDE](https://www.arduino.cc/en/software).
  * Channel 1 and Channel 2 on the Adri/Ardu-Scope are the Arduino analogue input [A0 and A1](https://www.arduino.cc/en/reference/board), respectively.  Just touching once of these ports, you should be able to see oscillations on the Adri/Ardu-Scope at 50Hz (Australia) or 60 Hz in other areas of the world.

  ## Motivation
   <img src="images\UWA-Full-Ver-CMYK3.png" alt="UWA logo"  align="right" width="150"/><br>
On many occasions you might need a [oscilloscope](https://en.wikipedia.org/wiki/Oscilloscope) or spectrum analyser.  The cost of USB scopes has significantly dropped over the last few years, allowing me for example to use the [2-channel, 10 MHz pico-scope 2000 series](https://www.picotech.com/oscilloscope/2000/picoscope-2000-overview) in my teaching at [The University of Western Australia](https://www.uwa.edu.au/) - this is as a excellent tool to looking and generating signals and giving students a face-to-face demonstration of data collection.   <b>But what if the cost and specifications of even a USB scope like this is beyond that required ?  What if I want to get an oscilloscope into the hands of every one of my students, but the cost of existing solutions does not scale where I have very large class numbers ?</b> <br>
This work considered how to make an [oscilloscope](https://en.wikipedia.org/wiki/Oscilloscope) and [spectrum analyser](https://en.wikipedia.org/wiki/Spectrum_analyzer) that could sample signals at around 153 kHz, more than adequate for audio, accelerometer, vibration and ultrasonic (40 kHz) investigations.  The hope here was to be able to create University level laboratories for our students who are remote (isolated by COVID), to get hands on, practical experience with signals and [time-series](https://en.wikipedia.org/wiki/Time_series) data collection.  All that's required is a ~$5 Arduino and the software tools on this site to create a very practical learning environment.  If you try this tool and think it useful, please let me know and where used/publicised, please promote and cite the project in any published work (see link on this site).   
Features of the [AdriArduScope.py](AdriArduScope.py) interface include: <img src="images\About.png" alt="About"  align="right" width="550"/><br>
* Two (2) channels supported, allowing (sequential) display of both channels
* High speed update to the display interface allows "real-time" interaction with the signals being received
* Sampling at up to 153 kHz - the sampling rate (display range) can be changed to allow sampling over many seconds
* External trigger (10 microsecond pulse) generated on Arduino port D4 - this is consistent with the wiring using for standard [HR-S04 Ultrasonic sensors](https://core-electronics.com.au/tutorials/how-to-use-ultrasonic-sensors.html).  Trigger delay allows signal capture after trigger event
* Amplitude and offset adjust available from the interface
* Save data to internal memory
* Save data to local drive (for post analysis in tools such as excel)
* Oscilloscope, Spectrum analyser, Spectrograph (from V0.2) and Cross-correlation analyser - The cross correlation analyser works in two modes: In a screen shot is saved to memory, the cross-correlation of the signal is obtained with the stored memory.  If the scope if setup to acquire data from both channel 1 and channel 2, the cross-correlation can be performed between Channel 1 &2.

