# CohhVatars Showcase
Idea for end of Stream.


The idea would be to add a banner or are at the bottom of the stream for when the stream ends. It could show case different CohhVatars by users typing in chat. 

Using Godot I have created the following short example using my CohhVatar. 

[![CohhVatar Example](https://img.youtube.com/vi/p0F6zTdH4wk/0.jpg)](https://www.youtube.com/watch?v=p0F6zTdH4wkE)

As you can see in this example, My avatar starts from the left and moves on a conveyor belt along the screen to the right side of the video. 


## How Its Made
Here is a rough break down of how its made. I have no clue how the backend of CohhVatars work so there may be a cleaner way to make it. 

### Godot Project Settings
To render a transparent background, we need to change the following setting:
Project Settings -> Rendering -> Viewport -> Enable 'Transparent Background'

### Godot Breakdown
Within the main node, I added 3 child nodes: Character Body, One for the gears, one for the rail. 
However if CohhVatars can be sent from the backend as a completed PNG, we could swap the character body out for a TextureRect(?) or similar and have it moved that.

### Godot Scripts

Cohhvatar Movement GDScript
```
CohhVatar movement:
extends CharacterBody2D

const SPEED = 70

func _physics_process(delta):
	velocity.x = 1 * SPEED
	move_and_slide()
```

Gear Rotation GDScript (This could be replaced with an animated gear script)
```
extends Sprite2D

var rotation_speed = 1

func _physics_process(delta):
	rotation_degrees += rotation_speed

```

### OBS Settings
New Source: Game Capture 
Enable: Allow Transparency. 
