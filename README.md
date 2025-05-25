# FlawlessAbby-Assignment
## How to use:

- the arrows are pickable objects, press E to pick them up
- Press I to open the inventory
- Hover over a slot and press the left mouse button to drag it around.
- Release the mouse button to drop the object
- You can drop the object over at another slot or at the viewport (the big blank space under the slots)
- press the X button to close the inventory or press the esc button.
- When approaching an NPC press F to fire the dialogue.
- Keep pressing F to skip to the next lines.

## Design decisions

### Item PickUp
For the pick up items i simply created an interface that handles the pickup event and called it from the player.
The function is overriden in any bluprint that implements that interface.

### Inventory system
Created an actor component for the player called Inventory. designed to handle the inventory and adding items into it. 
with an event dispatcher that keeps updating the items whenever it is called.

### Data assets (ughh I LOVE ME SOME DATA ASSETS)
In order to create as many pickup items and objects fast, i created a data asset with some simple attributes that can be read from any blueprint. And can be easily reconfigured.
The DAs are the array of items inside the inventory compoenent.

### Drag & Drop
to drag and drop items or slots within the inventory window. I designed a seperat slot widget that overrides the onDragDetect and OnDrop functions.
Having a seperate widget for one thing makes designing much easier, more readable and reusable.

### ViewPort slot 
Also a seperate widget. Made to override the OnDrop function, in order to drop items in it and view the objects either larger id 2D or 
in a 3D view.

### Render Target && SceneCaptureComponent2D
*"I am not gonna lie i had troubles with them, which lead me to love them even more, now that i understand how powerfull they can be." - Ebben*
When dropping the items on the view port a mateial of a render target texture takes over to view a world spawned object.
The object is a simple BluePrint actor with some functions to rotate and zoom using the SceneCaptureComponent2D.
Material is created to cut out the sky or the background from the object and show only the desired object with a translucent background.

### Dialogue System
Implemented another interface to NPCs in order to allow the player to interact with them.
Creating a widget of the dialogue that runs an array of string made inside the NPC.

### Bonuses
- Added a Forgot Note button to remove the selected item from the array gracefully.
- Positioning the dialogue relative to the speaker

## Things that could've gone better with more time.
P.S. I took the librty to recoreded my own time of development: 3h 49 min (not including the README)
- The feel and polsih.
  - i would've added a hover effect on the slots. and a drop effect on the viewport slot.
- the positioning of the dialogue box.
  - I calculated the desired size of and tried to clamp it to the screen but there is some wrong offsets.
 
## This is it
Thank you again for considering me :>

