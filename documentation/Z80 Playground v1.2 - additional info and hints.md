# Z80 Playground v1.2 - additional info and hints

## Notes

Questions asking for pointers from S Cousins


 - Nomber of vias, via concentration per cm squared
 - 2 or 4 layer boards used for SC103, etc.


## From SE.EE chat

 - [My initial question](https://chat.stackexchange.com/transcript/message/69179896#69179896)

### Nick Alexeev


> I don't see a compelling reason to put the CH375S USB module on the bottom. Maybe the module ended up in that position because of a PCB layout error. He wanted to have it on top, but didn't mirror the footprint.
> 
> I don't see a compelling reason why the CH375S USB has headers sticking up. [Was it cheaper to assemble that way?] I would point them down. Or not populate the headers at all and leave the decision to the final assembler.

### Lundin


> That one looks as if the main intention was for board-to-wire ribbon cable, rather than board to board.
> 
> One thing that's great in general is to go for 2xn socket strips of the "bottom entry variety" They are ordinary socket strips but with a hole through them so that you can make a similar hole in the PCB too. Then you can contact a header strip either from the bottom or the top and it will be a great electrical and mechanical connection no matter.

Regarding via concentration:

> I'm not sure if there's any particular number. If you have lots of high speed/RF stuff then you'll want to sprinkle vias all over. If it isn't anything like that, then you'll need far less vias.
> 
> Also it depends on the complexity of the ICs naturally. If it's some SOIC 20 part or if it's a massive BGA with two hundred pads.
Looking at this little PCB in front of me it is roughly 50x30mm and it probably got... I dunno 200 vias? One 48QFP MCU, one 28 QFN MCU, two QFN RFICs, maybe 5 or so other mixed signal or regulator ICs. 6 layers
Out of that at least 50 vias are around the tx and rx RF paths
> 
> The difference in price between 2 and 4 layers is nothing these days, unless you have the production volumes of Apple or something. There's basically no reason to use 2 layers any longer. Assuming some standard FR4 1.6mm

### rdtsc


> If you can do it on two layers with more vias, and price is a concern, then go for that. If price is less a concern, go with 4-layer. Harder for others to copy/make though.

