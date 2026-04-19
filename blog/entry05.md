# Entry 5
##### April/19/2026

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

