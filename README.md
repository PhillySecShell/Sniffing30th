# Sniffing30th
Event Project: Wifi and Bluetooth sniffing, flash mob style in the Philly 2600 House.

Conceptually, monitoring transient Rf traffic through business and personal space is *good* even before Zero Trust and BYO Device topics. Setting up a Proof of Concept is very attainable with nominal hardware and effort. Devices can free-range or be statically placed and report metadata to a more robust server. (like WiGLE & Kismet...or you can invent your own wheel)

As an exercise: Place a Kismet server on a private Wifi network with remote devices (as many as possible!) remotely reporting in as carried by participants. Monitor a large space. Grab a lot of Data. See what breaks.

## Handorf's Law 
(note: this is named for Mrs. Handorf, not the good Dr.)
### Don't Be Creepy
In order for this to be pleasant, fun, legal...not only should we not be obnoxious, we should really be stealthy. Most folks will react to "Doing an Rf study" with boredom (if not, invite them). "Hacking your Bluetooth signal" will get you the wrong kind of attention from some folks you don't want to mess with. *Even the software we will use implies ~listen only/do no harm. We might want to do something like this again someday too...

## Prep:
A Linux-y base system is assumed...copypasta will be Debian dialectically ...this should not discourage use of other OS's (yes, yes it should).
### Hardware
To work as a remote source a device will need an interface it can listen on, that is one device for control and one(radio) for listening. Some things make this easy, some difficult.
A Linux Distro "on the metal" with an extra WiFi card is optimal...*lots* of other stuff will work.
 
### Software
Kismet can be installed generically via apt.  
Even if you install that way you may want to start with the quick guide as it has prerequisites and troubleshooting that may help later...
https://www.kismetwireless.net/docs/readme/quickstart/
Devices intended for routing have great radios, but you might need to cross compile your own (Kismet Discord rocks. They really answer questions)

## Finally
In the end, after short talks (in a loud public space) we should be able to:

1. Connect to our Private AP (SSID and password in exchange for your email...)
1. Run a one liner like:
`<kismet_cap_Linux_WiFi --connect [Kismet Server IP]:3501 --source wlan1:name=your-name,filter_locals=true>`
1. See packets in good form being received from your device by our server.

Barring thermal events an unwanted attention the .kismet file would represent most of the Wifi and Bluetooth at 30th Street Station for the scope of the run.
