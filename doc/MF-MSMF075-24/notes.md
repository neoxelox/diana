I think you are assuming too much about these devices.
You have a "hold" current and a "trip" current.

The device is guaranteed not to open below the hold current and it is guaranteed to trip
by the time you reach the trip current. Between those two numbers, the behavior of the device is
not guaranteed, so you better not design a circuit that depends on what happens in that range.

For example, if you use a Polyswitch with a hold current of 500 mA and a trip current of 1A, all you know is that up to 500mA, it will not trip. And when it gets over 1A, it will definitely trip. In between, say, at 600 mA
or 750 mA, what happens is not certain and is dependent on ambient temperature and how long the device is subject to the current, among other things. For example, a 500/1A device might work at 600 mA, but after a whole hour at that current, it might finally trip. Or it might not. There are no guarantees of what it will do in the "no man's land" between the hold and the trip rating.

So if you have a circuit that will blow up at 700 mA, you better not use this device to protect it. You need one with a "trip" rating below 700 mA. And since most of these devices have a trip rating that is 2x the hold rating, a 700mA trip device will probably have a 350 mA hold rating. If you will be in trouble if your circuit trips and shuts off at 350 mA, you can't use this device.

In short, circuits whose protection device needs to function within a narrow, accurate range can't use these devices. If you need something that will definitely hold at 500 mA and definitely trip at 600 mA, a Polyswitch isn't going to work for you. My experimentation with miniature circuit breakers shows they behave about the the same. Breakers (and Polyswitches) are not very precise devices.
