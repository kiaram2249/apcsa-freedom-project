# Tool Learning Log

## Tool: **Godot**

## Project: Educational mini-game Or Simulation about the Environment

---

#### October/5/2025:
**Introduction to Godot**

* I was trying to install **Gobot** onto my school chrome computer, but I was very confused in how to input it into my **IDE**. So, I search [Godot Web Editor](https://editor.godotengine.org/releases/latest/), in order to use **Godot**. By using this editor I was able to start my new project, however using this editor I wasn't really downloading or setting **Godot** on to my laptop. I'll try and do that tommorrow, cause I need a little help in setting it up.
  
* Anyways, I was able to use the editor and I created a file called **MyFirstProject**. Once I created my file from the wed editor, I decided to focus on learning how to function **2D mode**.
    * I went and learned how to make my first **Scene** and **Sprite**.
      * How I created my **sprite**:
        * I needed to go to **Scene panel** and click `Node2D`. Once I did that I needed to click **Add Child Node** and search `Sprite2D`.
      * The **sprite** would appear underneath my `Node2D`.
        * Since I now have my `Sprite2D`, I can finally add an image to the **sprite**.
          * I needed to drag and drop `icon.svg` onto the `Sprite2D` node or into the Texture field in the Inspector in order to print out the image. When I did that a little Godot robot head appear in the 2D view.
         
<img width="1360" height="467" alt="image" src="https://github.com/user-attachments/assets/59b1a519-77de-41db-9cc7-62e7fe10ca6c" />

* For my next learning log I want to try making my imagines move by using the keybroad keys, and maybe adding more sprites as well. But for now my main prioritie is to download **Godot** onto my laptop so that I can use it into my **IDE**. That shall be my goal for tommorrow Freedom Project during class.
---

#### November/2/2025:
**Godot Web Editor Features**

* Since I can't download **Godot** onto my school chrome, I am still using the [Godot Web Editor](https://editor.godotengine.org/releases/latest/). So, for today's learning log, I decided to learn how to upload an image from Google onto **Godot**, and how to add a **Sprite** in order to make that image move around when the user is using there mouse key or arrow key.

* Creating a **scene** and adding a **sprite:**
  * I needed to create a scene with a **Node2D**, this is a **root node**. After that I began to add a **Sprite2D** node as a child of **Node2D** and I assigned my image to it by setting the **texture** property in the **inspector**.
* Writing the **script** for movement:
    * So, I needed to attach a script to the **Sprite2D** node, and by using the script I was able to make a code that allows the user to move the image by using the arrow keys or the mouse. 

**The code that allows the image to move around by using the arrow keys or mouse:**
```JS
extends Sprite2D

var speed = 200 // speed is set to 200 units per second

func _process(delta): // _process is the funcation that is called every frame
    if Input.is_action_pressed('ui_right'): // moves to the right
        position.x += speed * delta // delta ensures frame rate-independent movement
    if Input.is_action_pressed('ui_left'): // moves to the left
        position.x -= speed * delta // decreasing the x-coordinate
    if Input.is_action_pressed('ui_down'): // moves up
        position.y += speed * delta // increasing the y-coordinate
    if Input.is_action_pressed('ui_up'): // moves down
        position.y -= speed * delta // decreasing the y-coordinate
```

* This script moves the sprite in the 2D space based on user input, using the arrow keys to control the movement. Also, the speed of the movement is frame rate-independent, so the sprite moves consistently regardless of the system's performance.


**Takeaywas:**

* I need to make sure that I assign the image to the **sprite**.
* I need to write the movement code and attach it to the **Sprite2D** node.
* To ensure the scence is saved and to play/test it by using the play button.
* To use **print statements** because print statements are helpful when debugging and verifying the script.
---

#### November/15/2025:
**Platformer**

**Sources:** [Godot 2D Platformer Tutorial](https://www.youtube.com/watch?v=S2NG6fobarM)

* To set up a basic platformer level, I begin by creating a **root node** such as a **Node2D** and adding a **TileMap** or static platform nodes to form the ground and platforms. Next, I made sure to define **collision shapes** so that the player can interact with the environment properly. Then, I imported the player's artwork, adding a **Sprite** or **AnimatedSprite2D** and setting up the animation frames. Lastly, I attach a **CollisionShape2D** that fits the player's **sprite**, and **configure collision** layers and masks.

  * **TileMap** is where you can actually paint tiles ``Building``
  * **TileSet** is where you're editing tile properties ``Editing``

* Once I set everything up, I begin to attach a **GDScript** to the player and defined the key variables including movement such as speed, jump force, and gravity.
  
  * ``_physics_process(delta)`` function implement horizontal movement based on player input, apply gravity, and handle jumping when the player is on the floor.
  * ``move_and_slide()`` or ``move_and_collide()`` moves the character and detects grounded status.

* Once inputting those functions in the **script's** I needed to test the **scence** and tweak the movement values, the **collision shapes**, and the **sprite** alignment until everything feels smooth.

**MY CODE:**

```JS
extends CharacterBody2D

@export var speed = 200
@export var jump = -400
@export var gravity = 1000

var vel = Vector2() 

func _physics_process(delta):
	var move = Input.get_axis("ui_left","ui_right")
	vel.x = move * speed
	
	if !is_on_floor():
		vel.y = vel.y + gravity * delta
	else:
		if vel.y > 0:
			vel.y = 0
	
	if Input.is_action_just_pressed("ui_jump"):
		if is_on_floor():
			vel.y = jump
	
	vel = move_and_slide(vel, Vector2.UP)
	
	if move != 0:
		$AnimatedSprite2D.flip_h = move < 0
	
	if $AnimatedSprite2D:
		if !is_on_floor():
			$AnimatedSprite2D.play("jump")
		else:
			if move == 0:
				$AnimatedSprite2D.play("idle")
			else:
				$AnimatedSprite2D.play("run")
```
---

#### November/23/2025:
**Animations**

**Sources:** [How To Make 2D Player Animations In Godot](https://www.youtube.com/watch?v=H_3HEzOqso0) : [Godot Engine](https://docs.godotengine.org/en/4.3/classes/class_animatedsprite2d.html?utm_source=chatgpt.com)

* In this video, I learned how to set up a **2D animation** in Godot using ``AnimatedSprite2D``. First, I created a **SpriteFrames** resource and imported multipe frames to build different animation states. Then, I assigned that **SptiteFrames** to the ``AnimatedSprite2D`` node so it can play the animations.
   * ``AnimatedSprite2D`` uses **SpriteFrames** resource to define its animations.
   * In the SpriteFrames editor, I can set the **FPS** for each animation, and give animations names like **run**, **ide**, and **jump** for instance.
   * Using **loops** is optional when it comes into making an animation, but it just depends on what is needed.
* After creating the animations, the video showed how to control the animation from code.
   * ``AnimatedSprite2D.play("animation_name")`` switches between animations.
   * ``stop()`` can be used to stop an animation.
   * ``flip_h`` is useful to flip the sprite horizontally, so when the player changes directions, the animation plays correctly facing left or right.
 
**MY CODE:**

```JS
extends CharacterBody2D

@export var speed = 200
@export var jump_force = -400
@export var gravity = 1000

var vel = Vector2()

func _physics_process(delta):
    var move = Input.get_axis("ui_left", "ui_right")
    vel.x = move * speed

    if not is_on_floor():
        vel.y += gravity * delta
    else:
        if vel.y > 0:
            vel.y = 0

    if Input.is_action_just_pressed("ui_jump") and is_on_floor():
        vel.y = jump_force

    vel = move_and_slide(vel, Vector2.UP)

    # Animate
    var anim = $AnimatedSprite2D
    if move != 0:
        anim.flip_h = move < 0

    if not is_on_floor():
        anim.play("jump")
    else:
        if move == 0:
            anim.play("idle")
        else:
            anim.play("run")

```
---
<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
