You can download the IRobot Create 2 mathlab toolbox from online. This  Toolbox has all the functions you will need for interfacing with IRoomba.

This is the link to download the matlab toolbox- 
https://www.mathworks.com/matlabcentral/fileexchange/52644-matlab-toolbox-for-the-irobot-create-2

Download wifi scanner 3.4 from the internet 
Below is the link 
http://www.softpedia.com/get/Network-Tools/Network-Monitoring/Wi-Fi-Scanner.shtml

In order to use this library you would have to have your laptop connected to your IRoomba using an Edimax nano wifi chip adapter and a WiFi to serial for the serial port on the Roomba.

Connect to your Roomba using Wi-fi scanner .Right click on the wifi name and click connect. You will know it is connected when the device youre trying to connect to is in bold font.

Open matlab then start simulink. Go to file and open the library block .

Open the library block which has 3 blocks. The first is the wifi block which controls the connection to your local network
of 10.0.0.1   . This block has a function that will  allow simulkink to control the Roomba over wifi.  

The second block is the IR block. This block has the function to call  and make the IR sensors to read and report if there is an object in front of each of its sensors. When there is an object the sensor will report a 1. When there is no object the sensor will reprt a 0

The third block is the wheel block. This block controls the left and right wheel of the Roomba. Inside this block there is a function that controls the wheel speed of the left and right wheel.

Now open a new blank model on simulink and copy all three library blocks. Paste this into the new blank model
Move the Wifi block to the far left. Move the IR block to top center and move the wheel to the far right.

Now connect the from wifi block output "out1" to the IR block  input "wifiIn". Branch out a connection from the wifi block output "out1" into the wheel block input  "wifin" .

Now double click anywhere on the blank model space and type in "constant" and select the first one. Now copy and paste it so you
have 2 constant block. 

Connect one constant to the wheel block "left".  Connect on constant to the wheel block "right".

Now double click anywhere on blank model space and type "display" and click on it. Now connect the output from the IR block "IRSigs"
to the input of the display. This will show you the values of the ir sensors during the simulation.

Now go back to the constants and type -0.5 for left constand and 0.5 for right constant. You can type in any value from -5 to 5. Negative valuyes the wheel will spin backwards. Positive value the wheel will spin right. For this specific value  -0.5 for left and 0.5 for the right will cause the Roomba to rotate counterclockwise.

Now with everything connected we can go ahead and power on the Roomba by presssing the power button. Make sure we are connected to the Roomba by checking our wi-fi scanner app. 

We can now run the simulation on simulink and it will connect  to the Roomba and cause it to spin counter-clockwise. During the simulation you can put your hand in front of the roomba and it will display on the simulink display depending on which sensor your hand
is in front . There are 6 individual sensors that will display a 1 of your hand is in front or 0 if your hand is not in front.

You can change the values of the constants and this will change where your roomba will move. If you type 1 for left and 1 for right your Roomba will drive forward. If you type -1 for left andf -1 for right your Roomba will move backwards
.


