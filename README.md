M.I.M.P.

This is a project to get Mugen running on Pi 4.

August 5, 2021 UPDATE.

Mugen launching great from Retropie. 

Worked out keyboard mapper with qjoypad .

Have tested and been successful on following builds .

-Virtualman Pi 4 build 

-Back to future build by Micheal Miller 

-Regular Retropie 

Currently have have Mugen running at 45-50 fps. 
Have 40 mugens running great with following how to.

How to 

You will need 
- pi 4.
- micro sd 
- keyboard.
- usb mouse.
- pc to burn/etch sd card. 


1.Download os of choice.

2.update with
sudo apt-get update

3.Change gpu memory and install pixel 

Change gpu to at least 128 if necessary

This is done in raspiconfig under tools in pixel desktop or config.txt.

Install pixel if now if you don't have it .

4.Install Georges retropi setup extras

in terminal type

sudo git clone --branch emulator https://github.com/GeorgeMcMullen/rp-box86wine /home/pi/RetroPie-Setup/ext/rp-box86wineemu/ 

5.Update RetroPie-Setup and install scripts 

In retropie menu go to raspi-setup
Run retropie-setup update. 

Launch RetroPie Setup, go to "Manage Packages".
Then run the scripts in this order:

dependencies/mesa

experimental/box86

experimental/wine

6.Move game fies to /home/RetroPie/roms/wine/games
This can be done many ways .SSH, midnight commander to name a few.

7. Make Gnae Launch script

Use the shell script method. in terminal type 

sudo nano /home/pi/RetroPie/roms/wine/mugennamehere.sh 

replace mugennamehere with your mugens name .

containing the following:

#!/bin/bash

xset -dpms s off s noblank

cd "/home/pi/RetroPie/roms/wine/games/yourmugenfolder/"

matchbox-window-manager &

qjoypad "mugen" &

WINEDEBUG=-all LD_LIBRARY_PATH="/opt/retropie/supplementary/mesa/lib/" setarch linux32 -L /opt/retropie/emulators/wine/bin/wine '/home/pi/RetroPie/roms/wine/games/yourmugenfolder/mugennamehere.EXE'

Easiest way to do this is for your mugen is right click your exe and copy paths . 

Then replace "home/pi.......yourmugenfolder/" on cd line above.  with your paths to folder containing exe.

Then replace 'home/pi......mugennamehere.exe' on wine line with your paths to exe .

8.Replace wine desktop file with attached "Wine Desktop.sh" in this github . 

9.Open pixel desktop from retropie menu. Then install Qjoypad with

sudo apt-get install qjoypad 

10.Create a controller layout for mugen. 
Open qjoypad and make a layout called mugen. then map your controllers to buttons you wanna use in mugen. when you open mugen match these buttons.

11.Open mugen config in yourmugen/data/mugen.cfg most the time .

then find and change the following if necessary.

-GameSpeed = 60 

-Allowdebugmode = 1

-Allowdebugkeys = 1.    

-Video Settings

Width = 1280

Height = 720

-Fullscreen = 1

-Rendermode = System

-Blitmode = Normal 

-Joystick input for both players =0 

-Keep AspectRatio=1

12. open terminal type  sudo reboot 

13. Find mugen in retropie press play .

14. Map controls to match qjoypad.

15. Thats it. Repeat for your Mugens and enjoy . 

Frequently Asked Questions.


*Where/how do I get mugens?

visit 

https://www.andersonkenya1.net/files/category/3-full-mugen-games/

Then make a free account and download mugens. 

*Which Mugens work? 

Mugen 1.0 works best some 1.1 work.


*Why/whats debug key ?

-debug key is control+d. Allows you to see fps and info in bottom leftof screen .


*Will this script work for other windows games ?

YES! Heres a working list. Feel free to add too it .

https://retropie.org.uk/forum/topic/29241/the-which-games-works-with-box86-wine-topic-on-the-retropie-rpi4-400/62



*What to expect from M.I.M.P
- M.I.M.P stands for "mimp is mugen pi". So pi mugen stuff.
- We will be making a prebuilt Mugen, M.I.M.P screenpack and chars. optimized for pi 4.
- WE ARE WORKING ON A SCRIPT TO DOWNLOAD 10-20 MUGENS AND AUTO MAKE SCRIPTS THAT INSTALL WINE, MESA, BOX86, MUGENS, AND LAUNCH FILES.

*Resources
- Box86 Github - https://github.com/ptitSeb/box86
- Retropie Github - https://github.com/retropie
- Mugen - can be found many places. Orginal website is down.
- George in Retropie forum box86 topic. https://github.com/GeorgeMcMullen/rp-box86wine



*Props/Credit
- Box86.       
- Retropie.   
- Mugen.    
- Pi foundation.

