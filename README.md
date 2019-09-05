Please NOTE: this code is a stub, and not complete code.

This is a simple console application for setting frequency
and mode for rtl dongles, and transmitting using rpitx. 
It runs in Python3 using the tkinter library.

 --- For Receive ---

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


 --- For Transmit ---

You must have a raspberry pi, and F5OEO's rpitx software installed.
It can be obtained at: http://github.com/f5oeo
Then search for rpitx. It's one of the 1st repositories shown.

The rpitx software is configured to use GPIO 4 (pi pin 7) and
must be run by root. The code to start it uses sudo, so your
user ID must be in the sudoers file.

You also need to have arecord installed and working. Chances
are it is installed as part of your distribution.

A set of programs called csdr must also be installed. These you will
probably need to build yourself. It is involved.

CSDR can be found here: 

git clone https://github.com/simonyiszk/csdr.git

More information is here: 

https://github.com/ha7ilm/rpitx-app-note



 --- Remote and Local Radios ---

This was written so that the 1st RX and 1st TX device must
be local (the rtl dongle for receive must be attached to the
local usb port) and for TX, using the GPIO ports of the local 
computer (a pi zero in this case).

No other audio devices can be in use while transmitting or
receiving. In fact, when transmitting, the receiver is disabled,
and restarted when TX is finished. This is because the RX and TX devices 
share resources.

With in the console app itself is hardcoded links to the sound card
port itself (using play and arecord). It is doubtful that your
soundcard matches mine, so you MUST change these descriptions
to match your soundcard.

Search for: plughw:CARD=Device,DEV=0 and make your changes.

Receivers 2-5 and Transmitters 2-5 are assumed to be remote.
The code to use these is not yet written, but the stubs are there.

------------------------------------------------------------------

This was written on and for a raspberry pi 0 but should work
anywhere Linux and python and rtl-fm and rpitx  works.

This is (as of April 2018) very rudimentary. I'll add to it
as I have time.

- Kurt

