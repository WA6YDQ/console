This is a simple console application for setting frequency
and mode for rtl dongles. It runs in Python3 using the tkinter
library.

You must have a working installation of rtl_fm (and working hardware!)
and python 3 installed.

You must also have tkinter for python3 installed. If not, and you are 
running Linux (debian and it's derivitives) you can get them with:

sudo apt-get install python3 python3-tk

To play the output of rtl_fm as audio, you will need to have sox 
installed. The sox command "play" is used to play the audio.

sudo apt-get install sox

This also assumes you know the configuration of your sound devices.
If you need to (and is recommended) set up a file called .asoundrc
with the defaults to allow play (and aplay), and rec (and arecord)
to use your sound devices to work without interaction each time play 
and rec are used.

The easiest way to view your sound devices is with: aplay -L



This was written on and for a raspberry pi 0 but should work
anywhere Linux and python and rtl-fm works.

This is (as of April 2018) very rudimentary. I'll add to it
as I have time.

- Kurt

