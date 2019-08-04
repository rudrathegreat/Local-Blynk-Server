# Working with Local Blynk Servers
## Overview

This project is the proof-of-concept stage of a bigger, environmental project. In this project, I was able to - 

1. Send Auth Tokens to my email using the local server (the hard part)
2. Being able to send information from the Blynk App to the Arduino and turn LEDs on and off (the easy part)

## Files

There are several files which we are going to be using - 

> The `server-0.41.7.jar` file is used to start a local server on your computer
>
> The `blynk-ser-local.sh` file is used to connect our Arduino to our local server
>
> The `BlinkLEDArduinoBlynk.ino` file is a program that programs the Arduino to receive commands from a certain device via the local server and with those commands, do something.
>
> The `mail.properties` and `server.properties` files are used to configure the server

You can download the files by cloning the project. To do that, you simply need to click the `Clone or Downlaod` button and then select the .zip version. Then, in the Downloads folder, a folder should appear named `Local-Blynk-Server-master`.

## The Arduino Code

What we first need to do is create the code for the Arduino which will allow it to connect to a server (we will define which server in the `blynk-ser-local.sh` file) and then simply be controlled by our phone.

There are two main components to this code. The first is to configure the authorization (authorisation is you are in Australia) token. The Auth Token is used to differentiate one device from another and is used for security purposes - 

```C

char auth[] = "YourAuthToken";

```

And then implement the Auth Token when configuring the Arduino to connect to a server - 

```C

Blynk.begin(Serial, auth);

```

In this line, it is basically creating a Blynk connection to the Blynk Server. This line is specifying what type of connection it is (in this case serial) and the Auth Token.

You can find the rest of the Arduino Code is here - https://github.com/rudrathegreat/Local-Blynk-Server/blob/master/BlinkLEDArduinoBlynk/BlinkLEDArduinoBlynk.ino

## Starting a Local Blynk Server

Now we need to start the Blynk Server. To do that, we need to run the `server-0.41.7.jar` file in the terminal. We need to run the following command to not only start the server but also configure the server to our needs - 

```Bash

java -jar server-0.41.7.jar -dataFolder server_data -serverConfig server.properties -mailConfig mail.properties 

```

Now it should start a server on your computer's IP address. An IP address is a code that distinguishes your device from another. To check which IP address, simply type - 

```Bash

ipconfig getifaddr en0

```

That command only works if you are connected to the Internet via WiFi. To check your IP address if you are connected on Ethernet, replace the `en0` with `en1`.

## Connecting the Arduino to that Local Blynk Server

Once you have received your IP address, copy that and then open the `blynk-ser-local.sh` file. This file allows the Arduino to connect to our server. There is one line in particular that we need to edit and that it the following - 

```Bash

SERV_ADDR=192.168.1.103

```

Instead of that, it should be - 

```Bash

SERVER_ADDR={{YourIPAddress}}

```

Remove the initial IP address and replace it with your IP address. Once you have done that, save it and then run it by using the following command in the terminal - 

```Bash

./blynk-ser-local.sh

```

It will ask for what port your Arduino is connected to. Usually, you will only have one Arduino connected to the computer and so the `blynk-ser-local.sh` file will only show you one port number. Copy the port number which your Arduino is connected to and paste it after the colon (where you are supposed to put your port number in). The following image explains it a bit better.

Once you have done that, press enter and now your Arduino is connected to your server.

## Phone Time


## Conclusion

We are going to take this project further to incorporate many of our other projects, including the Water Quality Checking System (link below) and can make our lives much more relaxing and easier.

## Further References

> https://blynk.io
>
> https://www.arduino.cc
>
> https://docs.blynk.cc
>
> https://github.com/blynkkk/blynk-server
>
> https://github.com/blynkkk/blynk-library
>
> https://www.java.com/en/
>
> https://www.youtube.com/watch?v=YULg0IoqoZM&t=363s
>
> https://www.youtube.com/watch?v=fgzvoan_3_w&t=329s
>
> https://www.youtube.com/watch?v=33ynNkvfvWU&t=310s
>
> http://help.blynk.cc/en/articles/578659-local-server
>
> https://community.blynk.cc/t/local-server-email-will-not-send/2429
>
> https://community.blynk.cc
>
> https://community.blynk.cc/t/properties-files/8300
>
> https://community.blynk.cc/t/logging-data/2335/3
>
> https://community.blynk.cc/t/solved-how-to-configure-blynk-server/859/62
>
> https://www.youtube.com/channel/UCKWBP3MdpMQFdOCQ63mhC_Q
>
> https://community.blynk.cc/t/local-server-problem/16453
>
> https://www.instructables.com/id/How-to-Create-a-Blynk-Local-Server/

```Python

print('Thank You Sooooooo Much Blynk Team')
print('Thankyou for reading!')

```
