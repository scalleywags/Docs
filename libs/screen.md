
# Screen
* [screen](#screen-1)
* [capture (full)](#screencapture-)
* [capture (sub)](#screencapture-x-y-w-h-update--)
* [size](#screensize-)



## screen
The ``screen`` library provides a way of easily capturing screenshots.

````lua
-- Create a new buffer
local screen = require("screen").new();
````



### screen.capture( )
Capture the entire screen area.

````lua
x,y,w,h,img = screen.capture();
````



### screen.capture( x, y, w, h, [update]  )
Capture the specified screen area.

````lua
x,y,w,h,img = screen.capture(0, 0, 400, 400);
````

Optionally it can return only the sub-area that has changed since the previous call. If no pixels have changed since the previous call then the image will be ``nil``. The returned coordinates and size will correspond to the sub-area that has actually changed.

````lua
x,y,w,h,img = screen.capture(0, 0, 400, 400, true);
if (img) then
  print("area changed");
else
  print("area same");
end
````



### screen.size( )
Get the screen size.

````lua
w,h = screen.size();
````


