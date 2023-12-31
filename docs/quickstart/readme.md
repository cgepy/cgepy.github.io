you are at [docs](https://cgepy.github.io/docs)/[quickstart](https://cgepy.github.io/docs/quickstart) • get started with cgepy

### `#` Installing cgepy
Type the following into your preferred terminal/shell:

`pip install cgepy`
### `#` Getting started
####                Importing cgepy
Like every library, the first thing you want to do is import it.
```py
import cge
```
Because the library comes with a few extra utilities, you may want to import those too. (More on this later!)
```py
from cge.ext import clear
```
If you want, grab yourself some color as well. 
```py
from cge.colors import Color
```
####                Making a simple program
With imports out of the way, let's get started.
```py
my_canvas = cge.Grid() # Define a grid. The size is changeable and defaults to 20, and you can have multiple grids.
my_canvas.Update() # Clear the screen and print the game canvas.
```
This is a very simple template. However, you can easily tweak the appearance of your grid.
```py
# Assuming you want to edit index zero...
my_canvas.write((0,0), cge.Presets.green()) # Make it green!
# Or, if you wanted something different:
my_canvas.write((1,0), cge.Presets.blue()) # The square below the green is now blue!
```
This is the core functionality of cgepy, but there are easier ways to manipulate grids. Keep reading!
####                Adding a sprite
Now that you can edit the game canvas, you can also make a controllable sprite. However, cgepy already has a system for managing and controlling sprites, so we'll stick with that for now.\
First, create a new file or erase your old one. Once you are finished with that, your file should look like this:
```

```
Ok, seriously now. Adding a sprite is very easy.
```py
my_canvas = cge.Grid() # You'll need a grid for this.
my_sprite = cge.Sprite() # By default, the sprite will be at index zero. It's preset (but not limited) to be colored red.
my_sprite.Drop(my_canvas) # This will add the sprite to your grid. It can be in multiple grids at a time!
my_grid.Update()
```
Try it! It should look like a red square in the top left corner. Adding more is easy too, and so is removing them!
```py
my_sprite2 = cge.sprite(pos = (9,0), color = cge.Presets.yellow()) # On the other side of the canvas!
my_sprite2.Drop(my_canvas)
my_canvas.Update()

my_sprite.Remove(my_canvas) # my_sprite won't show up anymore.
my_canvas.Update()
```
####                Controlling a sprite
Yes, you guessed it. It's time to learn to move sprites around, access their position, and more.\
```py
# (in a new file)

import cge

my_canvas = cge.Grid()
my_sprite = cge.Sprite()

my_sprite.Drop(my_canvas)
```
As usual, the sprite will appear at index zero. There are a few ways to change this, though.
```py
my_sprite.Move("down") # Instead of down, cardinal directions, WASD, and IJKL also work.
my_canvas.Update() # Sprite appears one index lower.

# Alternatively, you can use Go() if you are moving the sprite more than one unit. 

my_sprite.Go((0,2)) # The position follows the normal (X,Y) format, not Y before X like the curses library.
my_canvas.Update() # Sprite appears two indexes below (0,0) 
```
####                Adding new colors

While cgepy does offer preset colors, you can also create your own with ease.
