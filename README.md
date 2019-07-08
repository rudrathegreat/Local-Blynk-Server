# Working with Local Blynk Servers
## Overview

This project is the proof-of-concept stage of a bigger, environmental project. In this project, I was able to - 

1. Send Auth Tokens to my email using the local server (the hard part)
2. Being able to send information from the Blynk App to the Arduino and turn LEDs on and off (the easy part)

## The Command to Run the Local Server

```Bash

java -jar server-0.41.7.jar -dataFolder server_data -serverConfig server.properties -mailConfig
mail.properties 

```

## Arduino Code

> https://github.com/rudrathegreat/Local-Blynk-Server/blob/master/BlinkLEDArduinoBlynk/BlinkLEDArduinoBlynk.ino

## .properties Files

> https://github.com/rudrathegreat/Local-Blynk-Server/blob/master/mail.properties
>
> https://github.com/rudrathegreat/Local-Blynk-Server/blob/master/server.properties

## The Hard Part

The hard part was not exactly the hard part. The mail.properties file is the file that allows the Blynk Server to email you [the Auth Token]. You can edit the email address in the mail.properties file. All it needs is your email address, the password of that email address, smtp server for your mailing application (unfortunately only supports Gmail) and the port. The local Blynk Server will access that email address and then write an email to you which includes the Auth Token.

## The Easy Part

This part can be done by anyone as this part is well-documented on the internet via videos and Blynk documentation.

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
