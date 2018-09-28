---
title: Thoughts on Different Platforms
updated: 2018-09-27
category: coatimunde
---

## TurtleBot

The TurtleBot is really what is getting this party started. It is essentially an open-sourced roomba with a laptop in its belly and a few cameras plugged in to it.

We actually won't be using it very much, as most of our work using the TurtleBot will really be done within the [Gazebo](http://gazebosim.org/). This will allow us to rapidly test algorithms in a simulated envirenment. 

## Quadcopters

Quadcopters are a fairly interesting robot as far as control systems go. They're basically just a testiment to power density of batteries combined with really cheap sensors thanks to cellphones turning into a nifty flying machine.

### How do they float?

They are able to float in place, and to do this they must produce thrust that compensates exactly for gravity. To make this task more difficult all of the torques of the motors must cancel out if you don't want the thing to spin around, so two of the motors spin the opposite direction of the others. To ascend, the four motors can all have a little extra juice added to go upward, and to descend they will just slow down a bit. Spinning like a top can be acheived by increasing the thrust on two motors while slowing on the two spinning the opposite direction, keeping the total thrust the same keeps the quadcopter at the same height but allows it to turn.

Flying around is done by appling thrust that is in a direction other than straight upward, decreasing the thrust on the leading edge and increasing it on the trailing edge will cause it to shoot in that direction.

### Control systems

All kinds of other nifty things can be done, they can fly through windows or put themselves in uncomfortable positions like upside-down or knife-edging around things... The control nerd wants to imagine that super accurate models are created and executed perfectly in some confirmation of math classes being useful in the real world. 

The reality is that they're almost all done using intentionally simple models in wild motion tracking labs (which we do have access to at RMC which really makes me want to do something like this) and just doing regression testing over and over until the robot figures out how to follow lines well.

## Artificial Potential Fields

So, given that for this project the drone would ideally be able to fly around in a real environment, not just in a lab with motion capture equipment wired up, and around arbitrary objects without a bunch of attempts to re-try motions, this won't do. 

The current idea is done all over the place, and will hopefully be fairly easy to apply to this project. The basic concept is you treat the robot like a very positively charged particle and the goal like a very negatively charged one. In the event that the goal is just a vaigue "go forward" then you treat the whole world as a gradient.  

Then, as obstacles are discovered, they are dumped into this little model as other positive charges, meaning that they would rapel the robot. They are stationary, so instead of moving toward the goal they create a series of valleys of lower charged areas between their higher charged areas.

The drone can then just travel toward lower charged areas but carry some inertia, as it does in real life. It should eventually reach the goal, even if this approach can cause some pretty stupid decisions. 

## Fixed Wings

My dream, which is clearly unacheivable given the time frame, would be to put this onto a fixed wing platform.

### How do they float?

They are not able to float in one place. They produce thrust that just pushes them forward and then wings do strange magic to the air to produce lift. This makes them easier to control in one sense, build them with wings tipped upward enough and a centre of gravity correctly placed and they essentially fly themselves. If you build a paper airplane and throw it then it may go somewhere. If you just throw a quadcopter it'll fly much the same way that bricks don't. 

Sadly this also means that the plane is bad at hovering in place, this means that making decisions quickly is important. It can also place a considerable constraint on the types of decisions that can be made. A quadcopter can just stop in place, do a 180, shoot straight up, drop straight down, whatever. The plane can't slow below a stall speed and usually ends up falling when it tries to steer, so steering a lot results in exciting crashes!

### Control Systems

Maybe I'll trick somebody else into putting together a very simple plane and a very simple control system for it, then I imagine that this same potential fields theory could be used but laying a big juicy reflected gradient left to right so that the plane would try to make most of its decisions based on going forward.

I fear this would result in too many crashes, but I also believe that in a sufficiently empty environment, maybe just the odd tree here or there, a plane could whiz along while only making modest impacts.

