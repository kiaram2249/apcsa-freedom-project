# Entry 4
##### 03/15/2026

### Content 

Over the past few months, I have been tinkering and experimenting with ideas for our freedom project, exploring different approaches and tools to bring our vision to life. Even though I am focused on building our **MVP** and following our plan, I am still taking time to experiment and learn about **Godot**. A couple of Mondays ago, for instancs, I learned how to create a **timer** in **Godot**, which gave me new ideas for how to structure time-based mechanics in our project. Even though I am still thinkering, I’m gaining a better understanding of how different systems interact and feeling more confident as my partner and I slowly bring our freedom project to life.

**EXAMPLE:**
**Code Timer**

```JS
extends Node

func _ready():
    var timer = Timer.new()     
    timer.wait_time = 3.0        // Set the timer to 3 seconds
    timer.one_shot = false       // Repeat the timer
    timer.autostart = true       // Start automatically
    add_child(timer)            
    
    timer.timeout.connect(_on_timer_timeout)

func _on_timer_timeout():
    print("3 seconds passed!")
```

### Engineering Design Process

I am slowly working my way through steps 3 and 4, which focus on brainstorming and planning. At this stage, my partner and I explored the direction of our game, carefully brainstorming to consider all the key elements. We discussed the art style, player mechanics, user interactions, and other important aspects of the experience. During this process, we were also able to write out a clear plan for the project. With that plan in place, my partner and I are now ready to move on to step 5, actually creating our game. This step is important because this will allow us to test our ideas in a playable form and apply what we have learned in Godot. Also, this can help us see what areas we need to improve on or adjustments that we need to make.

### Skills

#### Time Management

**Time management** is an important skill to have because my partner and I need to work on our project, especially when we are on a timeline. So, we need to make sure that everything goes smoothly and that we are on track with our plan. Time management is also important because we need to act onto our next step within our engineering design process, which is creating our game/prototype. Another reason in why time management is important because I don't want to stress and do things last minute.

#### Attention to detail

**Attention to detail** is an important skill because it will help us make sure that the game functions correctly. This is important because since we are starting to create our freedom project, we need to pay close atttention to details such as spelling things correctly and following proper syntax rules in the code so that it can help prevent errors that could cause the game to crash or behave unexpectedly.

#### Leadership

Having leadership is an important skill to have because I need to support my partner, since this project is a team effort and I don't want no one to be left behind. My partner and I need to make these steps together as a whole in order to make our project.

### Goal

I want my partner and I to start creating our game and bring it to life by the time that our spring break ends. I want to start building our game so that we can see what we can improve on and what adjustments we need to make as well.

### Professionalism

I'm conveying my learning by using all the things that I have learnt from the past and today [``Computer Science 9th, SEP10, & SEP11``] by learning, from **Tiny.cc/fccwd**, from **Html**, from **JavaScript**, from **Markdown**, and from my friends/peers as well. I have learnt many different kinds of coding and format, and how to use them as well. I am using all of my learning, and coding skills in order to make this first blog. I have used some of the **html**, as well I used some of the **markdown**. For instance, I used this ``*`` to make my words in bold, and I used ``_`` in order to make some words in italic.
