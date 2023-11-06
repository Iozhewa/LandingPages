# Cloud Security Project: The Deep Grey
Hello there~

_"It’s the week before the Year 12 Formal. Friends, family, and partners of Crabby College seek attendance… but who’s gonna contact them all? 
A guestbook website supplements this process. And a certain nerd wants to invite his pet Chihuahua through this system. 
SQL Injection within a user input field may allow insertion of additional data. If only you could find the right attack surface…"_

### The task:
- [x] Apply the Input Validation & Sanitization Process to find the Packet Tracer Flag
- [x] Traverse a files system in order to locate the right file for XSS (if only you knew what that was!)
<sub>no need to fret. you don't have to be a crabby canary to complete this challenge!</sub>

## First: Packet POV
![Let's see...](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/BetterBeginnings.jpeg)

Aw. Look at you. Sweet bundle of data. Created from controlled subparticle drift to signal machines at near
lightspeed. Adorable, waddling bits of bytes.

![It's dangerous to go alone!](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/hUH.png)
WOAH
That's a huge path! Be careful there -- some gateways may be closed, some computers may react badly to your signals...
so many risks at hand!
>[!NOTE]
>All data has the potential to turn malformed over the course of their packet journey. Let's trace this one to guide our personal goals

![Introduction to the Router](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/funnymachine.png)

This thing in the middle is the crux of this Local Area Network: `The Router`. The end-devices (Desktops and Laptops) access applications from the servers in isolation because of it. For our packet friend, _Packiceetus_, it's the biggest roundabout in the world.
Double click the router to optimize his route.

![CLI!](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/scary.png)

That's real technical, so let's have fun with it. Try some commands, much like asking the bus driver for directions.
Just... always thank your bus drivers. Start with
```
Router>
Router> enable
Router#
Router# show ip int brief
```
## Second: The Safest Path

![cable time B)](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/cables.png)

Here's a list of roads Packiceetus can go. We can check the road is there, but don't expect any roadside show; we have yet
to uncover the IP address of any devices...
```
Router# ping 10.13.37.1
Router# ping 192.168.1.1
Router# ping 10.176.120.1
```
This is Packiceetus' way of spinning around a roundabout. He's having a lot of find, mind you, but he's not going anywhere.
Let's try and get more information on these roads, these `cables`.
```
Router# show int g4/0
Router# show int g5/0
__________________________ <- Let's read through some info before moving on..!
Router# show ip int 3/0
Router# show ip int 3/0.10
Router# show ip int 3/0.20
```
Daunting, huh? Like a map before GPS. So let's highlight key info. Take your time reading, though!
We'll write notes too. All good hackers do so >:]
>[!NOTE]
>Here's some hints:
>1. The addresses (in #.#.#.#) are similar, but different
>2. Not all the roads are available
>3. There's more of `g3/0` than `g4/0` and `g5/0` combined!

![Line protocol is up (connected)](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/DefinedConnection.png)
______________________________________________________________________________________________________________________
![Line protocol is down (disabled)](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/CableDisabled.png)
______________________________________________________________________________________________________________________
![Internet address is 192.168.1.129/26](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/SimplifyingSpecificInterface.png)
______________________________________________________________________________________________________________________
![Internet address is 192.168.1.1/26](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/EncapsulatedVLAN.png)
______________________________________________________________________________________________________________________
![Internet address is 192.168.1.65/26](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/EncapsulationRevealingPathway.png)
______________________________________________________________________________________________________________________

Wanna compare notes? I hope you wrote some notes:
>[!IMPORTANT]
>1. There is a limited set of roads. `ip int brief` implied this, and `ip int g5/0` was proven to have no address.
>2. Cable `g3/0` follows an entirely different address class in relation to cable `g4/0`
>3. Cable `g3/0` has baby cables! What?!

## Three: Dive Right In
So far, this is a lot of information to take in. Which is fair -- Packiceetus can't exactly drive without knowing the way to go! There's one last thing worth checking before deductive skills (and sending Packi to space) will prevail.

The DHCP Pool.
>[!NOTE]
>While it's _fine_ to assign static IPs to devices every time they're added to a network, Sysadmins get lazy. What often
>happens instead is the initiation of the Dynamic Host Configuration Protocol. Fancy words for "We'll do it for you."

This is the biggest debrief yet. Take a deep breath... stretch...
```
Router# show ip dhcp pool
```

Woah!

![Non-functioning without VLANs (1/2)](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/AboveNetwork.png)
______________________________________________________________________________________________________________________
![Non-functioning without VLANs (2/2)](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/BelowNetwork.png)
______________________________________________________________________________________________________________________
![Functioning with One Red Herring](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/TopCorner.png)
______________________________________________________________________________________________________________________
![Functioning with One True Flag](https://github.com/Iozhewa/LandingPages/blob/main/Yeshua/assets/BottomCorner.png)
______________________________________________________________________________________________________________________
