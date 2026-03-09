# Entry 3
##### 02/8/2026

### Content

Over the past few months, I have been learning **Godot** by experimenting with its tool and features using the **Godot Web Editor** and now **Godot Engine**. I started with the basics, such as creating scenes, adding sprites, and moving them with keyboard input using GDScript. As I progressed, I learned more advanced mechanics like platformer movement, gravity, collisions, animations, moving platforms, scene transitions, player pickups, and etc. Through this tinkering process, I’ve gained a better understanding of how different systems in Godot work together and feel more prepared to begin building our game, moving to our next step within our plan.

**Code Moving Platform**

* This script makes a **Node2D** move back and forth between two points (``point_a``) and (``point_b``) at a constant speed. It also calculates the current velocity so other objects, for instance players standing on it, can use that information. Learning this can be useful because when my partner and I want to make a moving platform for our freedom project, I can use what I learnt from my tinkering in order to make that happen.

```JS
extends Node2D

@export var speed = 100.0
@export var point_a: Vector2
@export var point_b: Vector2

var direction = 1
var velocity: Vector2

func _physics_process(delta: float) -> void:
    var target = point_b if direction == 1 else point_a
    var move_step = (target - position).normalized() * speed * delta

    # Store velocity so the player can use it
    velocity = move_step / delta

    position += move_step

    if position.distance_to(target) < 4:
        direction *= -1
```


### Engineering Design Process

I am currently still on steps 3 and 4, which focus on **brainstorming** and **planning**. At this stage, I am continuing to learn the basics of **Godot** by practicing and experimenting with its features. Now, it is time for my partner and me to think more deeply about the direction of our game. We need to start brainstorming for real this time, because we need to consider all the key elements. We need to consider the art style, player mechanics, how the user will interact with the game. For instance, I need to think about what type of character the player will control, how the game will look visually, how I can implement the movement and animations I have learned in **Godot**, and what environmental information that we want to put onto our game. Planning is also important because it will help my partner and I create a clear roadmap for the project. We can plan out which role we can do. For example, I can focus on defining the game's structure, while my partner can work on the level design, and the information that we'll put. These steps are important because it will allow us to combine everything we have learned about **Godot** into a cohesive and organized game plan. However, next we will slowly begin step 5, which is **creating** our game. This step will alow us to test our ideas in a playable form and apply what we have learned in **Godot**. Also, this can help us see what areas we need to improve on or adjustments that we need to make. 

### Skills

#### Time Management

**Time management** is an important skill to have because my partner and I need to work on our project over the next up coming months. We need to make sure that everything goes smoothly and that we are on track with our plan. Time management is also important because we need to more onto our next step within our engineering design process, which is creating our game/prototype. Another reason in why time management is important because I don't want to stress and do things last minute.

#### Organization

**Organization** is an important skill to have because I realize that I need to be organize when working on the Freedom Project, when I am tinkering, and when making time for my partner. I also, need to improve on my organization skills because I need to make sure that we are following our plan so that we can slowly build the bigger picture of our project.

#### Consideration

**Consideration** is a skill that I need to work on because I want to design this game that can help people learn about the environment in a fun and esay way. Instead of overwhelming players with information, the game will teach environmental concepts through engaging gameplay and interaction. By doing this, the game can raise awareness while still being enjoyable, making learning feel natural and accessible for a wide range of players.

#### Attention to detail

**Attention to detail** is an important skill because it we help us make sure that the game functions correctly. Spelling things correctly and following proper syntax rules in the code help prevent errors that could cause the game to crash or behave unexpectedly. By paying close attention to these details, we can make sure the game runs smoothly and provideds a better experience for the player. 

### Goal

I want my partner and I to start creating our game and bring it to life. I want to start building our game, making a mini verson of it so that we can see what we can improve on and what adjustments we need to make as well. Also, I want to be able to start tinkering together with my partner during class or when we're on breaks. 

### Professionalism

I'm conveying my learning by using all the things that I have learnt from the past and today [``Computer Science 9th, SEP10, & SEP11``] by learning, from **Tiny.cc/fccwd**, from **Html**, from **JavaScript**, from **Markdown**, and from my friends/peers as well. I have learnt many different kinds of coding and format, and how to use them as well. I am using all of my learning, and coding skills in order to make this first blog. I have used some of the **html**, as well I used some of the **markdown**. For instance, I used this ``*`` to make my words in bold, and I used ``_`` in order to make some words in italic.
