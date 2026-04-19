# Entry 5
##### 04/19/2026

### Content

We’re getting closer to finishing our Freedom Project, and my partner and I have kinda been steadily working on building our MVP. Our project is a farming game, so we’ve been focusing on core features like animals, managing simple interactions, and building the basic environment. We decided to use Godot, which has been helpful as we learn more about game development and organize our work. Right now, our MVP is slowly coming together. We’ve been testing features, fixing bugs, and making small improvements along the way. It’s not fully complete yet, but it’s somewhat functional, which is our main gaol at this stage. As we move forward, we plan to expand beyond the MVP by adding more depth, like extra farming mechanics. It's still a work in progress, but we're making some steady progress and learning a lot as we go.

* The MVP was a challenge to make because we had to figure out what we actually wanted our project to be. Originally, we planned to create an environmental simulation, but we struggled with how to build that in Godot. Because of that, we decided to switch our idea to a farming game, especially since we had already worked with farming and crops in last year’s Freedom Project. So one of our biggest challenges was deciding on a clear direction for this year’s MVP. 

* Another challenge we faced was designing the layout of the game, especially when working with tiles. It took time to figure out how we wanted everything to look and how to organize the environment properly. We also ran into an issue with the camera view because when we first ran the game, it only showed a corner of the map instead of the full scene. We had to adjust the camera settings so the player could actually see the whole game area.

**THE MVP**

```JS
extends CharacterBody2D

const SPEED = 150.0
const JUMP_VELOCITY = -300.0

func _physics_process(delta: float) -> void:
	# Add the gravity.
	if not is_on_floor():
		velocity += get_gravity() * delta

	# Handle jump.
	if Input.is_action_just_pressed("ui_accept") and is_on_floor():
		velocity.y = JUMP_VELOCITY

	# Get the input direction and handle the movement/deceleration.
	# As good practice, you should replace UI actions with custom gameplay actions.
	var direction := Input.get_axis("ui_left", "ui_right")
	if direction:
		velocity.x = direction * SPEED
	else:
		velocity.x = move_toward(velocity.x, 0, SPEED)

	move_and_slide()
```

```JS
extends Area2D
func _on_body_entered(body):
    if body.name == "Player":
        print("Pickup collected!")
        queue_free()
```

```JS
extends CharacterBody2D

@export var speed: float = 200.0
@onready var sprite = $AnimatedSprite2D

func _physics_process(delta):
	var direction = Input.get_vector("ui_left", "ui_right", "ui_up", "ui_down")
	velocity = direction * speed
	move_and_slide()
	
	if direction != Vector2.ZERO:
		if abs(direction.x) > abs(direction.y):
			if direction.x > 0:
				sprite.play("walk_right")
			else:
				sprite.play("walk_left")
		else:
			if direction.y > 0:
				sprite.play("walk_down")
			else:
				sprite.play("walk_up")
	else:
		sprite.stop()
```

### Engineering Design Process

I'm no longer in step 3 (Brainstorming) or step 4 (Planning). Right now, my partner and I are mainly in step 5 (Creating) and step 6 (Testing). We've been working on building our MVP, which is our farming game, and we're starting to move toward our Beyond MVP by adding more features. While we're creating the game in Godot, we're also constantly testing it to catch bugs and fix errors early. This has been really important because we've already ran into issues, like problems with the camera view and how the tiles were set up. Looking at the EDP now, I also realize we're starting to move into step 7 (Improving) and step 8 (Communicating). We're improving our project little by little by fixing mistakes and making the game run better. At the same time, we're working on communicating more effectively, both during development and outside of class, so we can stay on track and keep making progress together. 

### Skills

#### Time management

Time management is an important skill to have, especially when we have a time frame and a plan to follow. When we had to work on the MVP, I have to admit that my partner and I weren't following the plan that we made. For this we had to work on the MVP within two days before school started. I would never do this again because within those two days I was over stress. So, my lesson from that is to never do work last minute.

#### Communication

Communication is a skill that I am improving on over the days, because I have been communicating with my partner outside of school in order to work on the Freedom Project. I need to work on communicating with my partner in school because I sometimes forget to talk to them about what steps that we should work on. However, outside of school I used Discord in order to communicate with them and to work on the project with them.

#### Problem decomposition

Problem decomposition is one of the skills that I have been learning and need to have because there's so much things that I want to do for the Freedom Project, but that would have been so much. So, I needed to break down those ideas into smaller pieces so that I can envison what I want to be feature into the game. So far, I have been doing good with that because during spring break, Robert and I were able to decided what we want to be input inside the game. Some of our old ideas were cut off, and it'll probably not be inclubed into the game. I'm glad that I have been slowly improving with this skill because now I know how to break things down into smaller/simpler tasks

### Goals

* To fix the MVP and to make improvement on it before the due date of the Freedom Project fair.
* Asking for help if needed instead of struggling on my own.

### Professionalism

I'm conveying my learning by using all the things that I have learnt from the past and today ```[Computer Science 9th, SEP10, & SEP11]``` by learning, from **Tiny.cc/fccwd**, from **Html** + **CSS**, from **JavaScript**, and from my friends/peers as well. I have learnt many different kinds of coding and format, and how to use them as well. I am using all of my learning, and coding skills in order to make this third blog. I have used some of the html, as well I used some of the markdown. For instance, I used this * to make my words in bold, and I used _ in order to make some words in italic.
