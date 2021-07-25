M.I.M.P.

This is a project to get Mugen running on Pi 4.

July 23, 2021 UPDATE.

Mugen launching great from Retropie. 

Worked out keyboard mapper with qjoypad .

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

3.Change gpu memory to at least 128 i use 256. 

This is done in raspiconfig under tools in pixel desktop or config.txt.

If you don't have pixel get it now .

4.Install Georges retropi setup extras

" git clone --branch emulator https://github.com/GeorgeMcMullen/rp-box86wine /home/pi/RetroPie-Setup/ext/rp-box86wineemu/ "

5.Update RetroPie-Setup and install scripts 

Run retropie-setup update. 

After update you should see a new subsection in "dependencies" and "experimental" with the scripts in them. 

They must be run in order and will produce an error if you try to install them out of order. 

Launch RetroPie Setup, go to "Manage Packages".
Then run the scripts as follows:

dependencies/mesa

experimental/box86

experimental/wine

6.Move game fies to /home/RetroPie/roms/wine/games
This can be done many ways .SSH, midnight commander to name a few.

7.Two options for making game script (I used .conf)

Option 1.

Create a file /home/pi/RetroPie/roms/wine/yourgame.conf 
containing the following:

DIRECTORY=/home/pi/RetroPie/roms/wine/games/yourgame/

PROGRAM=/home/pi/RetroPie/roms/wine/games/yourgame/gamelaunch.EXE

OPTIONS=

Option 2.

Use the shell script method. Create a file called:

/home/pi/RetroPie/roms/wine/yourgame.sh 

containing the following:

#!/bin/bash

xset -dpms s off s noblank

cd "/home/pi/RetroPie/roms/wine/games/yourgamefolder/"
matchbox-window-manager &
qjoypad "mugen" &
WINEDEBUG=-all LD_LIBRARY_PATH="/opt/retropie/supplementary/mesa/lib/" setarch linux32 -L /opt/retropie/emulators/wine/bin/wine '/home/pi/RetroPie/roms/wine/games/yourgamefolder/gamelaunch.EXE'


8.Replace wine desktop file with attached "Wine Desktop.sh" in this github . 

9.Open desktop install Qjoypad with sudo apt-install qjoypad 

10.Create a controller layout for your game. 
The Wine Desktop is looking for a a qjoypad layout with same name as the folder name of your game. Example disney controller layout will auto load if folder and layout have same name .  

Also if you are using .sh method just make one layout for all mugens titled "mugen". Then add this line to .sh files for mugen right above wine line .

qjoyoad "mugen" &   

11, Map controller with qjoypad. Update when done.
Remeber you have to do this twice for mugen. First in qjoypad then in mugen itself. You can copy your in mugen controls settings by editing data/mugen.cfg.

12. open terminal type  sudo reboot 

13. Find mugen in retropie press play .

14. Map controls to match qjoypad.

15. Turn joystick input off .it will be confused if not .



Add mugen as its own system in retropie

1. open pixel desktop .
2. edit es_systems.cfg 

sudo nano /home/pi/.emulationstation/es_systems.cfg

Add the following codeblock anywhere after <systemList>

<system>
<fullname>M.U.G.E.N</fullname>
<name>mugen</name>
<path>~/RetroPie/roms/mugen</path>
<extension>.sh .SH .conf .CONF </extension>
<command>bash %ROM%</command> copy this line from wine in es_systems.cfg
<platform>mugen</platform>
<theme>mugen</theme>
</system>

Also if do this remeber

If you u move games to mugen/games change your directories in launch scripts .
example roms/wine/games to roms/mugen/games 

Move your .conf or .sh files to /roms/mugen/games. 



Frequently Asked Questions.


*Where/how do I get mugens?

visit 

https://www.andersonkenya1.net/files/category/3-full-mugen-games/

Then make a free account and download mugens. 

WE ARE WORKING ON A SCRIPT TO DOWNLOAD 10-20 MUGENS AND AUTO MAKE SCRIPTS THAT INSTALL WINE, MESA, BOX86, MUGENS, AND LAUNCH FILES .

*What if I have to install a game ?
Install game in wine desktop launched with "Wine Desktop.sh" under wine in retropie. 
Then move games folder to /roms/wine/games or desired location . 
Normally things are installed to c drive of wine under /home/pi/.wine/cdrive/program files/game example . 
You have to "show hidden files " to see .wine folder .


*Mugen Settings 

Go to desktop find "mugen 001" for example.

Open mugen 001/data/mugen.cfg 

then find and change the following if necessary. Will find most in this order.

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


*Which Mugens work? 

Mugen 1.0 works best some 1.1 work.


*Why/whats debug key ?

-debug key is control+d. Allows you to see fps and info in bottom leftof screen .


*Will this script work for other windows games ?

YES! Heres a working list. Feel free to add too it .

https://retropie.org.uk/forum/topic/29241/the-which-games-works-with-box86-wine-topic-on-the-retropie-rpi4-400/62



*What to expect from M.I.M.P
- M.I.M.P stands for "mimp is mugen pi". So pi mugen stuff.
- We will be making a prebuilt Mugen, M.I.M.P, with chars and screenpacks.
- M.I.M.P prebuilt will be optimized to run on pi 4

*Resources
- Box86 Github - https://github.com/ptitSeb/box86
- Retropie Github - https://github.com/retropie
- Mugen - can be found many places. Orginal website is down.
- George in Retropie forum box86 topic. https://github.com/GeorgeMcMullen/rp-box86wine



*Props/Credit. Links above in resources. 
- Box86.       
- Retropie.   
- Mugen.    
- Pi foundation.

