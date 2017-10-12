# Digital-control-project-1
project for Dr.Bai ROOMBA

Attach wficard to Roomba
Install edimax wifi chip and connect to 
your roomba

First download icreate from the matlab add on package.
Set path into Mathlab folder under download

First you have to create a library 

Go to simulink and create library

Create a chart for the wifi initializiation

Go inside the chart and create a function that calls from workspace

then create a block that calls that function

click on the function block which takes you into the matlab workspace

create the function for the wif init function.
 
 create a function call tcpint

make a persisten class call obj

Use coder.extrinsic to call the function roombawifi

then use the same code with"assignin"

if statement if object is empty it will take the value of the function roombawifi
which has the ip adress to connect to the Roomba

create a global variable to take on the obj which has the value of the roomba ip address

That comppletes code for tcpint which connects the computer to roomba using wifi

highlight the library block and create a subsystem. Define the outputs and inputs

 now create a chart for the wheel controller

 inside the chart use the function to call on the premade function "SetWheelVelRoomba"
Create the 3 inputs which are left ,right, and wifi in. You can name it anything you like.
that completes the wheel part.

 create a chart for the ir. Inside the chart create a function that call the "rangeStateRoomba" function
inside the chart create inut from wifi in and output in my case was irsigs.

 Save the library

drag the library into worskspace. Connect the wifi block output into the ir block and whhel block as input. 
Create 2 constant input for the left and right wheel. connect the output of the ir block into a display .

 connect to your roomba using the edimax chip and wificard. Run the simulations and the display should display 1 or 0 in reltime 
depending if there are objects in front of the sensor or  not

 u can adjust the speed of each individual wheel . The range is -5 to 5 and this should 
change the speed of the wheels in realtime.


