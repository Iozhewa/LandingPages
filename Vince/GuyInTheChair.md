# Cloud Security Project: The Guy in the Chair
(Welcome!)

### Here's Your Mission:
- [x] Navigate a network topology via Packet Tracer to find your client's data
- [x] Navigate a systems directory to locate the correct file to alter precious information
(Don't worry, even someone who _isn't a Cranberry College Networking Student_ can solve this!)

## Part I: Do the Ping!
[Blueprint image]
[image https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#images]

You're not just a smart cookie, but a social one. Through some friends you share with Ned, you learn of a schematic he obtained to implement C-Snap.
It seems that he runs a trial service at a nearby place... Apple Dan High School.
> Let's go there!

[Wireless devices image]
> Crud, no WiFi...

Dressed as a student, you appear at AD HS (Not to be confused with actual Canberra highschool, ADHS). 
You run some basic diagnostics of the Cloud System by connecting to the internet...

> <sup>_Welcome students! Ask the IT teacher for the decryption. WiFi password is:_ **whzzdvyk!**</sup>

[Wireless connection UI guide]
> Well that's not working...
- [ ] Test entries for the AD HS WiFi
- [ ] [Find](https://cryptii.com/pipes/a1z26-cipher) a [cipher](https://cryptii.com/pipes/base32) that can [decode](https://cryptii.com/pipes/caesar-cipher) this (Hint: Which one shares a name with a salad?)

[Connection criteria image]
> Bingo!

Well now you can watch JackSepticEye's _Spiderman 2_ gameplay. Good for you.
Let's find a server room!
[server room image]
Wow, that was easy.
Let's open that router.
[CLI image]
> Eek! Scary, where's my cheatsheet?
Oh ho-ho. You sneaky snark.
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
- [ ] Open the IP Interface Brief to uncover traceable ranges
- [ ] Ping the `gateway` addresses to make sure they're responsive
- [ ] Try and modify the Interface Brief command for specific cables (Notice .10 and .20?)

> [!NOTE]
> Your sister/brother/cousin left you a note before your mission
> 
> <sub>"I did some digging. Don't know what it means, but my address is at the .65/26 range. DHCP..? Whatever, I'm turning it off."</sub>
