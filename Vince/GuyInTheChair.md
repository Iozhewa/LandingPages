# Cloud Security Project: The Guy in the Chair
(Welcome!)

_“Ned’s developed a secret College texting app called C-Snap. He monitors conversations at risk of exposing the system and intentions of cyberbullying, with a close eye on ‘privileged’ users (at a price). You happen to stumble upon the main computer on his lunch break, with just enough time to transcribe a code capable of receiving raw chat logs… and impersonating others.”_

### Here's Your Mission:
- [x] Navigate a network topology via Packet Tracer to find your client's data
- [x] Navigate a systems directory to locate the correct file to alter precious information
(Don't worry, even someone who _isn't a Cranberry College Networking Student_ can solve this!)

## Part I: Do the Ping!
![does it work now?](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/Introductions.jpg)

Hey, you. Dear sibling and budding systems engineer!
You're not just a smart cookie, but a social one. Through some friends you share with Ned, you learn of a schematic he obtained to implement C-Snap.
It seems that he runs a trial service at a nearby place... Apple Dan High School.
> Let's go there!

[What is this place...](https://github.com/Iozhewa/LandingPages/raw/main/Vince/assets/Vinny.pkt)

![does it work now?](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/Stage1.png)
> Crud, no WiFi...

Dressed as a student, you appear at AD HS (Not to be confused with actual Canberra highschool, ADHS). 
You run some basic diagnostics of the Cloud System by connecting to the internet...

> <sup>_Welcome students! Ask the IT teacher for the decryption. WiFi password is:_ **whzzdvyk!**</sup>

![Wireless connection UI guide](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/Passwords.png)
> Well that's not working... And the phone connected instantly!
- [ ] Test entries for the AD HS WiFi. Do this by double-clicking the laptop without a connecting line, and opening the `Wireless0` section just under `Interface`
- [ ] [Find](https://cryptii.com/pipes/a1z26-cipher) a [cipher](https://cryptii.com/pipes/base32) that can [decode](https://cryptii.com/pipes/caesar-cipher) this (Hint: Which one shares a name with a salad?)
- [ ] Question: What might you consider before connecting to public WiFi? Remember, the Internet is interconnected~

![Connection criteria image](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/FirstSuccess.png)
> Bingo!

Well now you can watch JackSepticEye's _Spiderman 2_ gameplay. Good for you.

## Part II: All Sneaky Like
Let's find a server room!

![server room image](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/ThatWasQuick.png)
Wow, that was easy.
Let's open that router.

![CLI image](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/wOAH.png)
)
> Eek! Scary, where's my cheatsheet?
```
Cheatsheet for Router Command Line Interfaces (Or CLIs)
__________________________________________________________________________________________________________________________________
Router> enable
Router#
  ~ Initializes the Command Line for interaction
__________________________________________________________________________________________________________________________________
Router# show ip int brief
+=====+ <-- Content appears here!
Router#
  ~ Provides a guide for all the addresses established for network communication
__________________________________________________________________________________________________________________________________
Router# ping [#.#.#.#]
+=====+ <-- Content appears here!
Router#
  ~ Sends a message to a device of my choice. These are just cables, so I get a response (5/5) or rejection (0/5) for a
    Default Gateway... Or a VLAN! Of course!
__________________________________________________________________________________________________________________________________
Router# show ip int [g#/#]
+=====+ <-- Filler
  Internet address is [#.#.#.#/#] <-- Need to cross-reference with the switches!
  Broadcast address is [#.#.#.#]
+=====+ <-- Filler
---more-- <-- Keep hitting enter until you see "Router#". It'll appear like a lot.
Router#
  ~ My new primary objective. If I can access the server room for a router, and get an IP range, I can find the classroom
    where my brother/sister/cousin's PC information is sent..!
```
Oh ho-ho. You sneaky snark.

<sub>Don't be afraid to ask the host for this part!</sub>

- [ ] Open the IP Interface Brief to uncover traceable ranges
- [ ] Ping the `gateway` addresses to make sure they're responsive
- [ ] Try and modify the Interface Brief command for specific cables (Notice .10 and .20?)

> [!NOTE]
> Your sister/brother/cousin left you a note before your mission
> 
> <sub>"I did some digging. Don't know what it means, but my address is at the .65/26 range. DHCP..? Whatever, I'm turning it off."</sub>

![This should be the answer](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/Elementary.png)
> This is huge! If this command line allows me to send signals to responsive devices... what if my sibling turned theirs off as an identifier?

## Part III: Where the Map Anchors the Ship
Which address ended up being your [brother/sister/cousin]'s? Among the files in the Server Room you find this:
```
Laptop 1: 192.168.0.104
Smartphone 1: 192.168.0.105
Laptop 3: 192.168.0.100
Smartphone 2: 192.168.0.106
Laptop 2: 192.168.0.102

Arnold: 192.168.1.69
Stephen: 192.168.1.4
Stanley: 192.168.1.66
Gregory: 192.168.1.2
Penelope: 192.168.1.67
Ronaldo: 192.168.1.5
Otis: 192.168.1.68
Danielle: 192.168.1.3

Benjamin: 10.13.37.5
Theresa: 10.13.37.68
Philip: 10.13.37.66
Wilf: 10.13.37.69
Harold: 10.13.37.4
Nimrod: 10.13.37.3
Quezon: 10.13.37.2
Pilates: 10.13.37.67
```
> [!IMPORTANT]
> None of these are actual addresses. In DHCP excercises, this structure is most commonly found in setting interface ranges. **never share an IP address**

Let's do a sneaky here.
![I'm pretty sure this never happens](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/Fantasies.jpg)

Now open up the computer terminal...

![Here's a series of images (1/3)](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/Ew.png)
![Here's a series of images (2/3)](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/THATSaTERMINAl.png)
![Here's a series of images (3/3)](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/OohLala.png)

And now we got a new list of commands:
```
pwd
  ~ A little reality check! Defines your current path in a set of files -- a directory
ls
  ~ Lists all folders and other content within a directory
cd
 --> cd ..
    ~ Takes you back one step
 --> cd [filename]
    ~ Takes you a step deeper within a file system
cat [filename]
  ~ If the file is in (txt), it can be printed within the terminal! Otherwise things might get cramped
clear
  ~ Provides a blank state for your terminal
```
>[!NOTE]
>Here's your final challenge! Work together with the host of this task. There's a lot of strange things your sibling downloads into this directory, all recorded in the audit logs of the database. This is the place Ned stores information for pinned messages on C-Snap. Exploit it to find a 'flag' file and win!

![What to expect](https://github.com/Iozhewa/LandingPages/blob/main/Vince/assets/Screenshot%202023-11-07%204.07.01%20AM.png)
## Reflection
So obviously, that's not how people _actually_ hack distributive systems.
Cloud storage is an alleviation from physical hardware; naturally people want to protect it.

What your actions today alluded to was a `Man-in-the-Middle` attack. You found an access point, acquired sensitive data, and were able to use it for personal exploits. That's a dangerous thing (and I'm proud of you).

In addition, you accessed a cloud 'hybrid' network. Both private for the audits in Ned's system, and public for all of his clients. There is a sweet spot where these things can be balanced. If this challenge entertained you in any way, please, continue the conversation. Cybersecurity is a terribly wondrous thing.
