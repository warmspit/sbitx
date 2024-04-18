FT8 List Unix App
![FT8 List Unix App](piFT8.png)

FT8 List Web App
![FT8 List Web App](webFT8.png)


# Improvements and fixes that I find useful.

(This branch is at this more than 6 commits ahead of afarhan/sbitx:main from 2024 02 13.)

## Hardware

The hardware I use is sBitx V2 upgraded to V3 as described in the document:
sbitxv3 PA changes and measurements
https://docs.google.com/document/d/1HvpgnS6zuPcygxmB6lvFZztqSGPLlWYzVGHhytWvQG4/edit

## 2024 04 18:

sbitx-oz7bx v3.02.0016

Improvements in this version:

### Web App in FT8 Mode: World Map with grids plot.   
A Robinson projection world map is displayed to the right* of the two FT8 Lists.
*(if the window is wide enough )  
The default "seen" behaviour is that all grids found in the current FT8 Lists are plotted.
That means only grids seen during the current web session. (The lists can grow very large and maybee to large!). If the App is reloaded the "seen" plot is cleared.  
Grids that has been logged are displayed in darkgreen, unlogged grids in yellow and grids logged during the current session are displayed in red. The plot can be toggeled on/off with the "Seen" button.  
The "Logged" button toggles display of all logged grids in green on/of.  
The map can be zoomed by the slider or the mouse wheel. Map position change is done by left mouse drag.
Mouseover on the map causes display of longitude, latitude and grid.  
Alt click in FT8 Lists causes caller lookup in qrz widow.

### FT8 mode: Only wipe QSO info if new call  
The QSO info fields are not cleared on actions (macro or FT8 List click) if the called station matches the CALL field (grid field might be filled). 

### FT8 mode: The FT8 lists are cleared when changing band.  
The old FT8 messages from another band was confusing.

### FT8 mode: Web message queue overrun fixed.  
The size of the web message queue (q_web) size was to small (even without my extra markup) and caused missing FT8 messages in the web FT8 lists.

### Web App: Band selector "radio" buttons.  
The band selector buttons now behaves like radio buttons and indicates the selected band plus current memory slot (1 -4).


## 2024 03 22:

sbitx-oz7bx v3.02.0010

N.B. two new sqlite indexes needs to be created:

    CREATE INDEX gridIx ON logbook (exch_recv);

    CREATE INDEX callIx ON logbook (callsign_recv);

Both the Unix App and the Web App now has the lists in FT8 mode decorated.
Callsigns of callers and grids that has been logged are now displayed in green,
and the ones not in the log are displayed in red.

An experimental world map with logged grids as red dots are displayed in the Web app.

## 2024 02 25:

Updated the code with 

Bechmans sound fix https://github.com/sbeckman/sbitx-clickfix and

sound output option: https://github.com/sbeckman/sbitx-sound-output-control 

## 2024 02 21:

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
