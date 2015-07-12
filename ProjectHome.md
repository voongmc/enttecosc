# What is EnttecOSC ? #

Quick Demo http://www.youtube.com/watch?v=owGylkQp2iE


---


EnttecOsc is a software program driver for the Enttec USB PRO Dongle. The program listens for incoming Open Sound Control messages in the format '/dmx channel(int) value(int'),     e.g. ' /dmx 1 255 ' will set channel 1 to the value 255.
EnttecOsc acts as a delegate between some other software program and the Enttec USB PRO Dongle.  When I say 'some other software program' I mean a program with OSC implementation (http://en.wikipedia.org/wiki/Open_Sound_Control) ,  such as MAX/MSP, Processing, Pure Data, etc.

# How can I contact you? #

I am currently setting up a website - http://www.zxinteractive.com/wp , should be up 1st Feb 2011, will set up a category for posts relating to enttecosc and the DMX Focus App.
Also use my youtube channel on the Demo link above.

# Why did I write it for an Enttec Dongle? #

The Enttec USB PRO Dongle is by far the best spec dongle, with excellent build quality and is reliable, it also processes on board, cutting down cpu on your own machine. I am by no way associated with Enttec, but I believe their products to be supperior to similar dongles.


# Will it run on Windows? #

Yes, its written in JAVA and will run on a JAVA Virtual Machine, so I have tested it on Vista, XP and Windows 7.


# Will it run on MAC  ? #

Yes, I personally use a MacBook Pro, MAC OSX 10.6.4, and developed the software on Netbeans.

# Will it run on Linux  ? #

Well, I have not tested it as of yet.

# OK, How do I install it ? #

Download it and follow instructions in the 'Install' file. Mac users may have to use 'chmod -R +rwx' on the directory that they download the zip file too.

Windows users should 'save' to their desktop and not 'open' as windows will bury the file in a temporary folder that has security restrictions on it and cannot access JAVA.

# Is there an App for that? #

Yes, its called DMX Focus and has been submitted to the app store.

# OK, I have downloaded the DMX Focus App, but how do I get it to talk to the EnttecOSC program ? #

This can be done in several ways.

## Option 1 (connect iPhone to router) ##

If your pc/mac is connected to a WIFI network via a WIFI router then your computer will have been assigned an IP address. Find out what your IP address is by looking in your network settings, or in MSDOS just type 'ipconfig' or in TERMINAL type 'ifconfig' . Now that you know your IP Address, go to settings in your iPhone, select your WIFI network which can be found under 'General' (the same network your computer is connected too) then select  DMX Focus and under 'Settings there is a field called 'IP Target' , so set this to the IP Address of your computer. Now the DMX Focus App will send data to your computer. - router should already have network password

## Option 2 (computer to computer network) ##

Set up an ad-hoc (computer to computer network), i.e. share your computers network, and connect your iPhone to that network, again you must create your own IP Address or note the one that the Ad-hoc network assigns itself, then type this into the DMX Focus App settings. - advise adding network password

## Option 3 (MAC only) ##

You could use the 'internet sharing' option, again you need to note the IP Address. - advise adding network password

NOTE - in windows make sure the firewall has not blocked port 50000 (or what ever port you entered in the enttec.properties file)

# Can I add a list of DMX fixtures to DMX Focus App that will need focusing beforehand ? #

Yes, under the notes tab you can add a list of channel fixture addresses in the form e.g. '1 -- 2 -- 3 -- 4 -- 5' etc'  etc, so when clicking on NEXT/PREVIOUS in the focus tab, the App will add 'full' focus to the current fixture and slowly 'clear' the previous fixture so the user will not be kept in the dark. The user can move up or down the channel list by simply clicking on NEXT/PREVIOUS.

# OK, I have the DMX Focus App, so what do I set in the Iphone 'settings' in order for it to talk to my computer? #

Just set the 'IP Target' field under DMX Focus in iphone settings to the IP Address of your computer, the IP Address can be found at the bottom of the EnttecOSC display, make sure your wifi is turned on in both the iphone and computer.  The other fields in the iphone settings i.e. port number, namespace, max channel value, min channel value may also be changed.


# Why did I write the program? #

I recently attended a theatre lighting course and realised that theatre techs spend a lot of time up ladders shouting down commands to guys at DMX lighting desks to "turn on" "turn off" fixtures. I have see a few expensive systems using radio to send commands direct to the desk, but not all theatres can spend that kind of money, so i write a driver to listen for OSC messages and then write them out to a Enttec USB PRO Dongle, so i have submitted an app to itunes (its called 'DMX Focus' ) to hook up to the driver and send full / clear messages to the dongle, so the guy up the ladder can control the fixtures and avoid getting his/her hands burned adjusting the lighting. The iphone app can be connected to a computer via the wifi router or using an ad-hoc computer network.
The driver can also be used for the usual suspects, i.e. max/msp, processing, puredata, supercollider, etc.




# EnttecOSC crashes / will not run, so where can I get exception  output? #

Try another port number, I have seen Windows 7 ignore port numbers above 49999, so try a lower port number, 12001 seems to be a good choice for Windows based machines, so basically change the 'oscport' in the enttec.properties file to another number and run the program again,  windows firewall should throw up a popup asking if you want to give access to this program, so click 'yes' .
The common error I see is that rxtxcomm.jar and rxtxSerial.dll are not installed in the correct loction, so repeat the steps in the 'Install' file.

If all else fails try this..

Run enttec\_driver.jar from MSDOS (windows) of Terminal (Mac) by navigating to the directory containing enttec\_driver.jar  and typing 'java -jar enttec\_driver.jar' . This will kick off the program and output the error, 9/10 times the program will fail because the parameters in the enttec.properties file are incorrect, namely the serial id field, e.g. com3 instead of COM3 (case sensitive) etc, or in the case of MAC OSX, file permission restrictions, so remember to do a chmod 777 on the directory containing enttec\_driver.jar file.




# Other libaries/software/help used to create this project #

I used a combination of Netbeans, processing core libarary, OSCp5, various serial drivers and some magic dust to get this working :)

http://java.com/en/download/index.jsp
http://jlog.org/rxtx-win.html
http://www.enttec.com/support-center/kb/article/000033
http://www.ftdichip.com/Drivers/VCP.htm



