Mugen running on Pi 4 . Aka M.I.M.P.

This is a project to get Mugen 1.0 running on Pi 4.

Currently,11/20, best way to achieve this is through Box86.

Box86 works with wine, in this document also works with Lutris.

Currently have have Mugen running at 45-50 fps. 

Many characters tested ex, deadpool, captain America a bunch more. 

You will need 
- pi 4.
- micro sd 32gb recommended.
- keyboard.
- usb mouse.
- pc to burn/etch sd card. 

How To Run Mugen 

- Download Twister OS.
- Burn Twister OS to micro sd with BalenaEtcher.
- Put sd in pi power on. 
- Customize twister OS look. Gui will guide you.
- After Twister setup. Connect to internet. 
- Download Mugen 1.0. 
- Move Mugen folder somewhere to find. Ex /home/pi/mugens
- Open Lutris on twister desktop.
- Click "add game " navigate to your mugen .
- Match mugen resolution with resolution in Lutris. 
- Click Launch
- Map controls to keyboard. If you want.
- FIGHT !

Mugen should open and play fine. 
For controller config and better play see optimising below.

Lutris Settings 
- Make a "Windowed Desktop" same resolution as your screen.
- More coming soon.

Optimising 
- To map controller like keyboard and mouse use qjoypad.
- If you autostart qjoypad on boot with controller configured. No keyboard or mouse is required.
- Kill all background processes you can before starting.

Wanna and to your pi 4 OS? 
- Check resources below Box86 github has source code .
- Over time will have M.I.M.P as a package, hopefully,with needed dependencies.


What to expect from M.I.M.P
- M.I.M.P stands for "mimp is mugen pi". So pi mugen stuff.
- We will be making a prebuilt Mugen, M.I.M.P, with chars and screenpacks.
- M.I.M.P prebuilt will be optimized to run on pi 4.
- M.I.M.P will be loaded on Lutris.net for easy install.
- Launching directly from retropie / frontends, through launch script.

Updates 
- Will update doc within the week with better performance .
- Updates will come as necessary. Still early in box86's "life".
- Will update when Vulkan drivers are better implemented on pi 4.


Resources
- Box86 Github - https://github.com/ptitSeb/box86
- Twister OS Website - https://twisteros.com
- Lutris Website - https://lutris.net 
- Lutris Github - https://github.com/lutris
- Retropie Github - https://github.com/retropie
- Mugen - can be found many places. Orginal website is down .



Props/Credit. Links above in resources. 
- Box86.       
- Retropie.
- Twister OS.   
- Mugen.
- Lutris.       
- Pi foundation.

