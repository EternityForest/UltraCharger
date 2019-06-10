# UltraCharger
Highly experimental I2C solar battery charger frontend 


This little board is smaller than a buisiness card and basically acts as a frontend for ORing two inputs(2.1mm barrel),

putting the power through a buck-boost into a battery, measuring battery voltage and charge current, and providing 3.3v on the STEMMA
connector through a LDO regulator(Efficiency isn't an issue given the very low current needed to wake up one a second and do MPPT, and
occasionally report status).

There's no UI, it's meant for use with an ESP8266 breakout and UI via a remote machine.

This makes a ton of compromises to be smaller than a business card and on 2 layers. It's not tested and won't be till
I get the PCBs back. However it has been designed to be about as safe as any other consumer microcontroller-powered charger, when used
with the appropriate protection PCB for your battery.

The core is a 1A switching regulator set to 21V, for charging Ryobi One+ batteries. Even if the MCU fails it will not reach unsafe voltages.

That also should be witin the safe range of any decent 4S lithium protection PCB, unless they make thise crappier than I think,
so you should be able to charge 12V batteries and various LTO batteries.


You likely won't be getting more than 12-20 watts with this thing, and efficiency isn't fantastic, but it should be robust against all manner or transients and bad connections, aside from reverse battery which it handles with a clamp that trips the fuse or protection circuit you hopefully are using.
