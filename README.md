# Intro to Virtual Reality
Today we're investigating different Virtual Reality toolkits. We're looking
for libraries people have built that will help us get started making our first
VR game. I'm especially interested in:

* Building a basic virtual room with blocks
* Building interactive buttons
* Building levers, knobs
* Walking around
* Practiciting hand navigation

I saw a local Seattle company, Tomorrow Today Labs, publish their own
NewtonVR library that seems to deal especially with buttons, levers, doors,
and allowing characters to pick up, drop, hold and throw objects in their
VR environment. Although I definitely want to find a library that gives me
good objects where I can build "widgety" environments with buttons and levers
the NewtonVR library just doesn't *look* very good. We'll see what NewtonVR
offers after investigating VRTK, which looks more popular.

* VRTK https://github.com/thestonefox/VRTK
* NewtonVR https://github.com/TomorrowTodayLabs/NewtonVR
* Tomorrow Today Labs http://www.tomorrowtodaylabs.com/

# Installation

First, clone the VRTK toolkit.

```bash
git clone https://github.com/thestonefox/VRTK.git
```

I'm using Unity version 5.6+. I immediately see an error message telling me
about this discrepency. I ignore the error. Let's see how far we can go before
this really becomes a problem.

I'm following instructions in the main VRTK repo.

I added the `VRTK_SDKManager` to an empty GameObject I created in the scene.

Cool. That all went well. And that's it for the instructions on the main repo.
Moving to their Getting Started guide. No real problems so far.

# Getting Started
My writing here is not intended as an actual reference. Follow the directions
in the Getting Started file for step-by-step directions. What follows in my
own text here is simply a narrative summary of what I've done, and any problems
I ran into along the way.

<https://github.com/thestonefox/VRTK/blob/master/GETTING_STARTED.md>

The Getting Started directions instructed me to drag a `VRSimulatorCameraRig`
into the scene, and find the VRTK_SDKManager script attached to the empty
game object and configure all SDK choices to simulator, click an "auto populate
linked objects" button and I'm able to press play and start the simulation.

I can click play to start the simulation. Immediately I'm able to move my mouse
and it directs what the camera is looking at in the simulation. I can press
`Left-Alt` to toggle to "move hands" mode and press `Tab` to switch between
the hands. Each hands shows up as a red and green dot with a small line
attached to it.

* `Left-alt` toggles "move hands" mode
* `Tab` switches between left and right hands
* `Left Shift` toggles between translation and rotation for hands
* `Left Ctrl` switches between X/Y and X/Z axis

All controls work and there's handy help text in the simulation screen.

# Example Scenes and Videos

OK, it turns out there's not much to see with just the Getting Started
scene. I'm happy to see everything runs correctly without and errors.

To get a good overview of what all the VRTK library provides I suggest
watching the videos associated with the example scenes:

<https://github.com/thestonefox/VRTK/blob/master/EXAMPLES.md>

The videos show off what's in different scene files showing examples of
how to use the whole toolkit.

You'll see how to teleport, see different modes of transportation, see
controls available, see how to grab objects, how to snap objects into a
good position when you grab them, and all sorts of other stuff.

Scrubbing through these videos alone will give you a good sense of the
state of VR development today! The best part is that video narrator, and
original creator of VRTK, always points out contributions made by other
developers. The entire toolkit is an open source project where people
can come together and build what they need for projects.

## Ways to Move in VR
* **Touchpad Walking** - move around by using one of the touchpads on a wand.
* **Physical Walking** - have your VR gear detect your position via headset / 
  hand controller tracking.
* **Amplified Walking** - allow players to toggle an amplified form of walking
  where each step they take in the real world will translate to 2x, 3x, Nx
  steps in the virtual world. This allows users in a 10x10 real space
  traverse distances in a 20x20 (or more) virtual space. Allowing users
  to toggle whether their walking is amplified allows them to walk across
  a great distance, then turn it off and interact in normal distances again.
* **Teleport by Pointing** - Allow users to point to where they want to go
  and click to activate an instant teleportation. One downside of this is
  users may be able to teleport themselves to an area of a world that they
  shouldn't be in. Various other scripts in VRTK enhance and restrict
  teleportation. For instance, one script prevents users from teleporting
  into space where there's not enough vertical space to stand up. Another
  prevents them from placing their "chaperone bounds" (the virtual walls
  that bound the physical player space) intersecting a wall object.
* **Teleport by Village Map** - I'm a sucker for village maps. This
  teleportation scheme provides the user with a table with objects on
  it. The objects represent a "village map" of the area the player is
  in. If they point to an object on the map then it teleports the player
  to that space. This is a good way to restrict teleportation to only
  places you want the player to be able to go to.

## Available Mechanical Controls
* **Buttons** - Buttons can be pressed and acivate events. They can be
  activated by rigid bodies. The controller isn't a rigid body until the
  trigger button is pressed down.
* **Sliders** - Sliders can go horizontal, vertical, or at an angle. Sliders
  have a resolution associated with them, so a slider can have a resolution
  of "5" with only 5 positions, or it can have a resolution of 100.0 with a
  very smooth sliding effect over a large range of numbers.
* **Levers** - Levers can be vertical or horizontal.
* **Chest** - Chests can contain things. They come with automatic hinges.
* **Drawer** - Drawers also can contain things. Things can't be grabbed until
  the drawer is open.  Like if the user puts their controller through the wall
  of the container clipping through it.
* **Radial Dial** - A dial that turns in a circle. Hmm. I wonder how well
  this can be adapted to a pirate wheel.

The videos are seriously good and short and easy to understand. Watch them! 

<https://github.com/thestonefox/VRTK/blob/master/EXAMPLES.md>
