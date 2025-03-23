# FrPalletizingSetup
This repo is a step by step instruction for settings up a Fairino palletizing solution.

## Contents of repo:
-   Rail Up documentation and set up instructions

Video for Rail Set up step-by-step:

    https://drive.google.com/drive/folders/1Kpjjic1A1EnLq9yDP_YpjaPuU1yFIZyL

If you run into problems not mentioned on this repo, try looking at the Inovance documentation here:

    https://www.inovance.eu/fileadmin/downloads/Servo_drives_and_motors/SV660N_Advanced_User_Guide.pdf


## Step 1: Putting your solution together:
Start by first hooking up your solution 

## Step 2: Set up Encoder
- When setting up the rail, you may get communication errors on the encoder that read E731.0
- If you see this, do the following:
    1) Flip up the screen at the top of the encoder and press "Mode" (or "Set" first, I can't remember as im writing this). It will then allow you to modify the register value that you'd like to edit.
    2) Use the up/down arrows to adjust the values of the register until you see get "h0d.20" and press "set"
    3) Here, you should see a blinking "0". You'll need to set that to "1"  (using the up arrow) press set and then power cycle.
## Step 3: Communicating the robot to the rail:
- The provided code should have the propper UDP set up, but you'll need to give it the values the first time you set it up. Screen shots of the correct parameters can be found in this repo.
 - In "Initial"->"Peripheral"->"Ext. Axis" select Ext. Axis + UDP.
 - Change exaxis number to 1
 - Edit the "Communication config" to have the following values:

    - IP address: 192.168.57.88
    - Port number: 2021
    - Communication cycle: 2ms
    - Packet loss detection time: 50ms
    - Packet loss times: 10
    - Communication interval: 50 ms
    - Automatic reconnection after interuption: enabled
    - Reconnection period: 2ms
    - Number of reconnections: 5
    - Position completion time: 1000ms

 - Click configure, load, and then save (the checkmark at the top)
 - Navigate to "Initial"->"Base"->"Coordinate"->"Ext. Axis"
 - Select extaxis1
 - Click edit, select "param config" and enter the following values: 
 ![alt text](image.png)[size=.20]
 - Click save and then the check mark at the top
 - Now you're good to go!
