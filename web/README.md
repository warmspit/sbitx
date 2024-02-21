
Improvements and fixes that I find useful.

The hardware I use is sBitx V2 upgraded to V3 as described in the document:
sbitxv3 PA changes and measurements
https://docs.google.com/document/d/1HvpgnS6zuPcygxmB6lvFZztqSGPLlWYzVGHhytWvQG4/edit

Most of my improvements are related to the very useful web UI and FT8 mode.

The SAVE button has been renamed to LOG as it just opens the log tab.
Log and Qrz tabs are now opened or updated when the LOG or ? buttons are clicked.
The LOG OK button now works and saves the QSO in the web UI (Afarhan fixed this 2024 02 13).

New knob button for showing or hiding the dial knob (Instead of clicking the frequency field).
New Sound button for muting the sound (useful in FT8 mode).

In LSB or USB mode the web UI waterfall can be clicked on an interesting signal, and the signal will be centered and just need fine tuning.

The frequency field will now react on turning the mouse wheel.

The frequency STEP choices now has a 500H step size.
The bandwidth BW now steps from 50 to 5000 in steps of 50.

In FT8 mode, when a CQ XXXX GGGG is clicked the XXXX callsign is checked against the LOG. 
If the callsign is found the latest LOG info is shown on a line and a QSO is not started.
If the callsign was not found the QSO is started as before.

