you are at [docs](https://cgepy.github.io/docs)/[quickstart](https://cgepy.github.io/docs/quickstart) • get started with cgepy

### `#` Installing cgepy
Type the following into your preferred console/shell: (command may vary based on operating systems)

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
from cge.ext
```
If you want, grab yourself some color as well. 
```py
from cge.colors import Color
```
####                Making a simple program
With imports out of the way, let's get started.
```py
my_canvas = cge.Grid() # Define a grid. You can have more than one!
my_canvas.Update() # Clear the screen and print the game canvas.
```
This is a very simple template. However, you can easily tweak the appearance of your grid.
```py
# Assuming you want to edit index 0...
my_canvas.write((0,0), cge.Presets.green()) # Make it green!
# Or, if you wanted something different:
my_canvas.write((1,0), cge.Presets.blue()) # The square below the green is now blue!
```
Try playing around with this for a little and see what you can make.
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
Try it! It should look like a red square in the top left corner.\
You can't interact with it, though. So why not learn h-
####                Controlling a sprite
Yes, you guessed it. It's time to learn to move sprites around, access their position, and more.\
```py
# (in a new file)

import cge
