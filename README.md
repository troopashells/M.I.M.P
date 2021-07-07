M.I.M.P.

This is a project to get Mugen running on Pi 4.

July 6,2021 UPDATE.
Mugen launching great from Retropie 

Have tested and been successful on following builds .

-Virtualman Pi 4 build 

-Back to future build by Micheal Miller 

-Regular Retropie 

Currently have have Mugen running at 45-50 fps. 
Have 28 mugens running great with following how to.

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

3.Install Georges retropi setup extras
git clone --branch emulator https://github.com/GeorgeMcMullen/rp-box86wine /home/pi/RetroPie-Setup/ext/rp-box86wineemu/

4.Update RetroPie-Setup and install scripts 
Run retropie-setup update. 
After update you should see a new subsection in "dependencies" and "experimental" with the scripts in them. They must be run in order and will produce an error if you try to install them out of order. Launch RetroPie Setup, go to "Manage Packages" (P) and then run the scripts as follows:
dependencies/mesa
experimental/box86
experimental/wine

5.Move game fies to /home/RetroPie/roms/mugens/games
This can be done many ways .SSH, midnight commander to name a few.

6.Two options for making game script (I used .conf)
Option 1.
Create a file /home/pi/RetroPie/roms/mugens/yourgame.conf containing the following:
DIRECTORY=/home/pi/RetroPie/roms/mugens/games/yourgame/

PROGRAM=/home/pi/RetroPie/roms/mugens/games/yourgame/gamelaunch.EXE

OPTIONS=

Option 2.
Use the shell script method. Create a file called: /home/pi/RetroPie/roms/wine/yourgame.sh containing the following:
#!/bin/bash

xset -dpms s off s noblank

cd "/home/pi/RetroPie/roms/mugens/games/yourgamefolder/"
matchbox-window-manager &

WINEDEBUG=-all LD_LIBRARY_PATH="/opt/retropie/supplementary/mesa/lib/" setarch linux32 -L /opt/retropie/emulators/wine/bin/wine '/home/pi/RetroPie/roms/mugens/games/yourgamefolder/gamelaunch.EXE'

After you've created either of these files, you'll have to restart Emulation Station in order for them to be picked up.

7.Launch game as normal retropie game.

8.Mugen Config

Go and edit settings as normal to make it full screen and other changes. Tons of info online for it . 

Where/how do I get mugens?

visit 

https://www.andersonkenya1.net/files/category/3-full-mugen-games/

Then make a free account and download mugens. 

Mugen Settings 

Go to desktop find "mugen 001" for example.

Open mugen 001/data/mugen.cfg 

Find and change the following if necessary. Will find most in this order.

-GameSpeed = 60 

-Allowdebugmode = 1

-Allowdebugkeys = 1.    

-Video Settings

Width = 1280

Height = 720

-Fullscreen = 1

-Rendermode = System

-Blitmode = Normal 


Which Mugens work? 
Mugen 1.0 works best some 1.0 work.

Why/whats debug key ?
-debug key is control+d. Allows you to see fps and info in bottom leftof screen .

Will this script work for other windows games ?

YES! Heres a working list. Feel free to add too it .

https://retropie.org.uk/forum/topic/29241/the-which-games-works-with-box86-wine-topic-on-the-retropie-rpi4-400/62


What to expect from M.I.M.P
- M.I.M.P stands for "mimp is mugen pi". So pi mugen stuff.
- We will be making a prebuilt Mugen, M.I.M.P, with chars and screenpacks.
- M.I.M.P prebuilt will be optimized to run on pi 4.
- Controller mapped to keyboard using joy2key. so keyboard isn't necessary, right now escape key is very necessary for mugen . 

Resources
- Box86 Github - https://github.com/ptitSeb/box86
- Retropie Github - https://github.com/retropie
- Mugen - can be found many places. Orginal website is down .
- George in Retropie forum box86 topic. https://github.com/GeorgeMcMullen/rp-box86wine



Props/Credit. Links above in resources. 
- Box86.       
- Retropie.   
- Mugen.    
- Pi foundation.

