### Important
* show a message if WebGL is not supported by the hardware (and some helpful resources)
* change the Ctrl+Shift+L shortcut to something else, to avoid Firebug confusion
* edit README.md to be more useful, now that we're almost done with the pre-alpha stage

### Soon
* add some GUI (zoom and rotation sliders, thickness & spacing, auto rotation)
* customize the visualization (transparency, view & draw mode, texture on/off)
* zooming should be done towards the cursor
* fix camera panning with right click
* preview pane in the lower right (showing the visible area of the webpage, like a map)
* need a reset/close button
* about box (controls)

### Next weeks
* implement the MOZ_dom_element_texture WebGL extension once it's finished
* handle the CSS transforms and z-index of nodes
* render some nodes differently based on their positioning (absolute/relative)
* add details for each node (id, class, code bubble)
* add save functionality to the edited code in the bubble
* implement a map of the DOM (tree structure, search, go to node)
* highlight a node and the children (glow, grayscale others, etc.)
* perhaps a zoom control that isolates a dom node and its children only
* the back of the webpage itself should, instead of a mirror image, display the entire source code
* display useful information on the sides of the nodes too
* hide/unhide nodes

### Following months
* add some lights, experiment with bump mapping
* export the visualization to other browsers (html, url, image, obj)
* handle mouse clicks on the webpage and seamlessly refresh the visualization
* better support for XUL

### Wacky ideas
* create some DOM art, so that it looks amazing in Tilt
* when we have live updates, we might even create Tilt movies! 
* minecraft?
* expose/ spaces/ mission control/ speed dial? that would be awesome!
* audio rendering (lol?!)
* a haptic map device so that we can feel the page in 3D
* easter eggs
