# Total hour spent: 8.3hrs

## 17 September 2026 - 1 hr
### Schematic
I’m designing a PCB Badge for Haven satellite event, I plan to make a blinky board nametag. I need to do the design in easyeda (which I’m not so familiar with) instead of Kicad to get discount price from JLCPCB. To start, I went to google the components I need to make blinky, and search up them in the easyeda library to put them into the schematic diagram.I’m looking for smd components so it looks better on the board compared to tht. For the NE555, I just follow the application circuit for Astable mode.

## 27-28 September 2026 - 1 hr 10 min
### Routing & designing
My friend draft a design for the PCB badge, so I start by importing the draft image into easyeda to have a rough shape of the hedgehog. I was searching for the footprint of the correct leds, there was so many type. Then I placed the components onto the board, and start routing them. I was figuring out how to flip the components to the bottom side, I went to google since I can’t find it out myself lol. Then, I got stuck on how to use copper pour in Easyeda it keep causing DRC error with no distance between route. I also drew a rectangle cutout for the lanyard to hold the board.


## 30 September 2026 - 37 min
### Routing again
The component I used was THT, so it was kinda ugly as it poke up through the board. I went to google the components (NE555 and CD4017) in smd, and search up them in the easyeda library to replace them with the THT components in the schematic diagram. It looks better on the board compared to tht. I simply replaced the CD4017 THT with smd schematic. Luckily I checked the datasheet again for the NE555 as I realised that the previous connection was for monostable mode. I rerouted the schematic for Astable mode.

## 9-10 October 2026 - 1 hr 47 min
I’m looking for smaller led to replace the one I’m using since it’s a bit big and bulky on the board. I was planning to switch to SK6812-mini. After switching all of them, I continued with the routing. I calculated the power trace width to support the current for 8 leds with online calculator.   Since the pcb badge is designed for the participants of Haven, I want to include the NFC to help them to check in. It would be such a cool feature!! LED + NFC!!!  So I imported a mini NFC footprint which I previously designed in my NFC keychain project to Easyeda. I routed the NFC and its R/C as a group before adjusting their position in the board. It’s mini and fit nicely in the board below the blinky system.  Welp, I sent my designed for my friend to check and realised my connection for the LED was wrong in the schematic, I accidentally connect a led to VSS instead of the output pin lol. So I went to correct it and double check all the other connections. I redraw the schematic to make it look neater.  I also added a CR2032 battery holder for power supply!! 


## 11 - 19 October 2026 -1 hr 40 min
EEEEEEE I just realised NE555 require 5v power supply while Cr2032 only able to supply max 3.3v power, which means that the blinky would not work with insufficient power.   I had to give up making the board blinky, I connected them in parallel, at least they can still turn the lights on rather than removing all the leds.
 On 18 Oct, I found out a Christmas tree blinky board, powered by Cr2032!! So i went to did some research whether 3v to run a blinky is possible, well i saw the hackster.io tutorial and they’re using Atiny to power the blinky. However, it’s a microcontroller although it’s cheap but it would require programming. Since i need to design the PCB in bulk, I try to avoid that as it would need me to manually upload the code one by one for ~100 pcb 0.0 

However that does give me a sense of hope that i could create a blinky board run with 3v using other ic!! I went to search up and found out more modern IC using CMOS which is able to run blinky mode on lower power.  I found 2 type of common IC for that, however TLC555 seems need 1 more IC to help to provide the pulse so after comparing their stability and price, I decided to use ICM7555.  I then drew the schematic according to the data sheet. For the value of resistor and capacitor, I calculated myself then send it to AI to check whether the value are okay.  Then i rewired the leds to 74HC4017D, since I have only 8 leds indtead of 10, I need to wire last pin to MR reset the ic early (i learnt this from ai hehe) 

## 21-22 October 2026 - 1 hr 20 min
It’s time to put them all together! Since I had changed almost the whole schematic, I had to redo the PCB layout. This time, I did it faster since I remember the basic control (flip to bottom side, shortcut keys, etc.)

I start with power route then to the leds. I oso edited some footprints (leds, battery holder). I almost forgot to add switch to my circuit.
As for the NFC, since we are making the PCB in bulk, adding the NFC IC would make it too expensive for us to produce, so i had to remove it QwQ.

I was still having trouble with copper pour, I keep getting 0 distance between the pour and the route. After looking into it, I realise i used the wrong function (slot fill instead of copper pour), so after changing the function, it finally work! YAY! 
Still gotta double check!

## 24 October 2026 - 40 min
After some double checking, I found that i accidentally connect the resistor to and instead of vcc. I also manually adjusted the trace width, idk why selecting the route width before routing still make it using the default width.

Added silkscreen for name and logos. :D

I think my board is ready!
