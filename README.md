# pysnip_tool_using_python
pysnip_tool_using_python


# Method 1 using pyscreenshot 
create a file grabfullscreen.py
```python
import pyscreenshot as ImageGrab

# grab fullscreen
im = ImageGrab.grab()

# save image file
im.save("fullscreen.png")

```
# For custom area 
create a file grabbox.py

```python 
import pyscreenshot as ImageGrab

# part of the screen
im = ImageGrab.grab(bbox=(10, 10, 510, 510))  # X1,Y1,X2,Y2

# save image file
im.save("box.png")
 ```
# Automated with multi-display functionality 

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

<img width="2560" height="1600" alt="monitor_1_2ad40e1a-ca0d-4c8e-bbcc-5f45b3fa76a5" src="https://github.com/user-attachments/assets/a1872f6e-bd62-4906-8d7b-a591df670d93" />



For more information, check the documentation [here](https://github.com/ponty/pyscreenshot).

