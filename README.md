# pysnip_tool_using_python
pysnip_tool_using_python


# Method 1 using pyscreenshot 
# pyscreenshot/examples/grabfullscreen.py

"Grab the whole screen"
import pyscreenshot as ImageGrab

# grab fullscreen
im = ImageGrab.grab()

# save image file
im.save("fullscreen.png")


# custom area 
# pyscreenshot/examples/grabbox.py

"Grab the part of the screen"
import pyscreenshot as ImageGrab

# part of the screen
im = ImageGrab.grab(bbox=(10, 10, 510, 510))  # X1,Y1,X2,Y2

# save image file
im.save("box.png")

# Automated with multi-display functionality 





# for more info, read these documentation here 
https://github.com/ponty/pyscreenshot
# PyScreenshot Tool Using Python

## Method 1: Using PyScreenshot

### Grab the Whole Screen

```python
import pyscreenshot as ImageGrab

# Capture the entire screen
image = ImageGrab.grab()

# Save the image file
image.save("fullscreen.png")
```

### Grab a Custom Area

```python
import pyscreenshot as ImageGrab

# Define the area of the screen to capture (X1, Y1, X2, Y2)
image = ImageGrab.grab(bbox=(10, 10, 510, 510))

# Save the image file
image.save("box.png")
```

This method can also be automated and works with multiple displays.
# Method 2: using mss 
https://python-mss.readthedocs.io/
```python
from mss import mss

# The simplest use: save a screenshot of the 1st monitor
with mss() as sct:
    sct.shot()
````
 # for multiple displays.
```python
from mss import mss
import uuid

def multi_display_screenshot(snip:bool):
  if snip:
    with mss() as sct:
        monitor_count=len(sct.monitors)-1
        print('No of monitor:',monitor_count)
        for i in range(monitor_count):
          file_name=sct.shot(mon=i+1,output=f"monitor_{i+1}_{uuid.uuid4()}.png")
          print("Screenshot saved to:", file_name)

multi_display_screenshot(True)

  

```
For more information, check the documentation [here](https://github.com/ponty/pyscreenshot).
