#  Automatic Water Barrel Filler  
Automates refilling a water barrel used for watering a small garden greenhouse. They didn’t want to plug in a pump every few hours only to have turn it off again ten minutes later when it has filled up again.
it could be controlled by a microcontroller.  
I also did not want the pump to switch on/off every second because of the water level jumping above and below a certain threshold. To fix this I used 2 float switches, one which is the maximum water level and one forthe minimum water level.  

#  Supplies  

Electronics:  
1x ATmega328P Xplained Mini with cable for programming  
2x polypropylene float switch  
1x 5v relay module 1-channel (i used a KY-019)  
3x male to female jumpers   

Bigger bits:  
1x old outlet power strip  
1x water barrel  
1x submersible pump with waterhose  
1x powerbank to power the ATmega328P  
1x plastic container to put the electronics in and keep them dry  
2x small triangle bracket or similar to mount the float switches on  

Tools:  
stuff to keep everything together with (duct tape, hotglue, screws)  
tools to remove bits of hard plastic (stanley knife, chisel, drill or something similar)  
screwdrivers

#  Step 1: Make Some Room Inside the Power Strip  
WARNING: MAKE SURE THE POWER STRIP IS NOT PLUGGED IN WHILE WORKING ON IT!  

Since we want the relay to be inside the power strip, some room needs to be created on the inside. So open it up and cut away some the metal and plastic pieces at the end of the strip so that the relay module fits inside.  

#  Step 2: Connect the Relay  
Now that there is room to fit the relay into, it is time to connect it up.

First off you need some more wire, so pull the power cable through a bit further and remove the outer casing of the cable that you pulled in. You need enough wiring so that you can reach the relay and go back to the original connection point.     
Now close the power strip back up and it is ready to be controlled by a microcontroller.  

#  Step 3: Install the Float Switches  
To know when the power strip needs to be turned off or on, we need some float switches installed inside the water barrel.  
Connect the float switches to the triangle brackets, and connect them to the inside of the barrel with screws or other means at the desired switching levels. also make a small hole in the barrel for the wires of the float switches to go through.  

Make sure to close up the holes with some hot glue to make it watertight again.  

#  Step 4: Connect It All Up    

We installed all the components, so lets connect them all up according to the image.  
I connected a plastic container to the side of the barrel to put all the electronics in, so that it won’t just be hanging around the side.  

#  Step 5: Creating the Program  

I mainly learned to code in C, so this project is written in C.    
Open AtmelStudio.    
Click on “File” -> “New” -> “Project”.    
Click on “GCC C Executable Project”. Give your project a name and location to store. Click “Ok”.    
Search for the ATmega328P. Click “ATmega328P” -> “Ok”.    
Click in the Solution Explorer on “main.c” to open the main program.   

#  Step 6: Adding the Code  

Copy and paste the following code in main.c   
[project02 code file.txt](https://github.com/Kartikborkar/M2_Embedded_ProjectType_Automatic_Water_Barrel_Filler/files/7642477/project02.code.file.txt)
#code present in makefile   

#  Step 7: Run and Test the Code
Connect the microcontroller to the computer and follow these steps to select the right tool and program the microcontroller.

Click on the hammer tool.  
Select the “mEDBG*ATML” debugger/programmer.  
Select interface “debugWIRE”.  
Click “start without debugging”.  

This will build the program and write it to the microcontroller.  

#  Step 8: Now for Real  

The barrel fills up until the top float switch is pushed up and waits  '
until the bottom float switch goes down for the plugged in pump to turn on again.



