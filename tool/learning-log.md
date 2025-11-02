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

* Since I can't download **Godot** onto my school chrome, I am still using the [Godot Web Editor](https://editor.godotengine.org/releases/latest/). So, for today's learning log, I decided to learn how to upload an image from Google onto **Godot**. Then I learned how to add a **Sprite** in order to make that image move around when the user is using there mouse key or arrow key.

* I first began to create a **scene** and add a **sprite**
  * I needed to create a scene with a **Node2D**, this is a **root node**.
  * After that I began to add a **Sprite2D** node as a child of **Node2D** and I assigned my image to it by setting the **texture** property in the **inspector**.
* Once I did that I than began to write the script for movement
  * So, I needed to attach a script to the **Sprite2D** node.
  * By using the script I was able to make a code that allows the user to move the image by using the arrow keys or the mouse. Once everything was done, I saved the scene and press the play button to test the scene. 

**The code that allows the image to move around by using the arrow keys or mouse:**
```JS
extends Sprite2D

var speed = 200

func _process(delta):
    if Input.is_action_pressed('ui_right'):
        position.x += speed * delta
    if Input.is_action_pressed('ui_left'):
        position.x -= speed * delta
    if Input.is_action_pressed('ui_down'):
        position.y += speed * delta
    if Input.is_action_pressed('ui_up'):
        position.y -= speed * delta
```

**Takeaywas:**

* I need to make sure that I assign the image to the **sprite**.
* I need to write the movement code and attach it to the **Sprite2D** node.
* To ensure the scence is saved and to play/test it by using the play button.
* To use **print statements** because print statements are helpful when debugging and verifying the script.
---


<!-- 
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
