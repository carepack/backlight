# [backlight]
## increase or decrease the backlight of your laptop (allows fine adjustments in low light environments)

### Problem description
The problem with binding brightness increase/decrease for your laptop to a keyboard shortcut is the size of adjustment steps that will be performed if you hit it. Often, in low light environments, you want to make fine adjustments to be able to adapt your screen backlight to the actual environmental brightness, but if you just use "xbacklight" with some key-bindings, chances are good your adjustment steps are too small in bright enviornments, or too huge in dark environments when you're working late at night. Let's just fix this.

### Solution attempt
[backlight] determines the step-size for the upcoming adjustment that a user wants by looking at the current value of the backlight brightness. If the backlight is bright already, chances are good you don't want to increment in 1% steps, but rather 5% or so. This script attempts to solve this problem by applying a quadratic function.

### Usage
Usage: backlight [OPTION]


Options:

--increase
  increases backlight brightness

--decrease
  decreases backlight brightness

--get
  gets current backlight brightness value (float)

### Keybindings
#### ~/.i3/config
bindsym XF86MonBrightnessUp exec $HOME/bin/backlight --increase

bindsym XF86MonBrightnessDown exec $HOME/bin/backlight --decrease

