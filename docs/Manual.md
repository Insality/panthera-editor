# Online Editor Manual

## Animation editing

### Editor zoom & pan

To move camera - hold left mouse button and drag it. Use mouse wheel to zoom in and zoom out.


### Change initial state of animation

To change initial state of any node - set animation time to 0 and edit node state in _Node info_ panel. Any changes at animation time 0 is changes in initial node state.

You'll see the mark "Initial state" on _Node info_ panel


### Set node parent

To change node's parent - press the _Parent button_ in _Tree View_. Then click on another node in _Tree view_ to make it as parent of selected node.
To remove parent - select already parented node and click _Parent button_.
To cancel _Parent mode_ click _Parent button_ again.


### Rename node

To rename node - double click it on node's name in _Tree view_. You can't use already existing node name.


### Add animation key

To add animation key you should edit values in _Node info_ panel. Modified values will mark with 🔸 symbol. Click on _property name_ to add animation keys to node timeline.
The animation time should be greater than 0. All modified properties will be added on timeline.
The new animation key can split existing animation key on two.


### Delete animation key

To delete animation key - select it and click delete button in _timeline key edit_ panel.


### Adjust animation key from _Node panel_

You can adjust animation key end values if you change values in _Node info_ panel and click on _property name_ to update existing animation keys in current animation time of this property.


### Adjust animation key on timeline

You can adjust timing of selected animation key on timeline. You can grab the start pin or end pin of animation line to adjust start/end animation time. Or you can grab the line itself to adjust both at one time.
You can grab only selected animation key.


### Copy animation keys

You can copy all animation keys from selected node and paste it to another node. All current animation keys will be replaced with copied.


### Reset property to default values

You can do a long click on _property name_ in _Node info_ panel to set values to default one. It is a vector of [0] or [1] values and origin image size for _size_ property.


### Draggable value fields

You can adjust values by dragging left/right with mouse from input field.


### Change animation timing

To change animation time click on animation time and enter new value (it should be greater than 0).

You will get the confirmation window with two options:
- Stretch all existing animation keys proportionally. So you can make animation slower or faster
- Don't change animation keys timings


### Upload your images to node

To upload image to your animations, just drag'n'drop you image right in the editor. You image will be stored in _Image cache_ and you can use it on another nodes. You can't upload several images with similar names, it will be replaced.


### Remove image, image stub

In _Node settings_ panel you can change the node image or remove it (it will return to empty square image)


### Image manual/auto size mode

There is _set image_ trigger to change image of the node in the animation. If your node has any "size" animation keys or origin size of the image is changed, the image will have "Manual" size mode, so any new image will keep node image size values.
Otherwise it will have "Auto" size mode and new image will set origin image size.


### Images cache

Any uploaded images saved in _Image cache_. You allow to use any of this image to set it on node, the _set image_ trigger has the list of images from this cache.
You allow to export _Image cache_ to Json file and import it later or send it with your project file. The images keep in base64 format.


### Project rename

To rename project open the _Projects_ window and use project name input field to change it name


### Share your project

To share your project - export it as Json and share it. Also your probably to import your Images to share it with project file.


### Defold *gui or *.collection import
It's able to import your nodes' layout from *.gui or *.collection file. To do this you should drag'n'drop this file to the Panthera editor window (you will see the drag'n'drop hint)
The *.gui will export all node structure with all node params (even the image name, but images itself should be imported separately).
From *.collection file - currently only node id, parents, position, scale and rotation


## Animation export

### GO export restrictions

Since in GO we can't animate some values, some of property will be not exported in GO export:
 - size
 - color
 - slice9


### Simple export

Simple export - the export with just one function with animation callbacks to make the animation flow.
It's useful to copy code to use it in your way. It's not force you to use module or additional functions/params like other exports do.


### Module export

Module export - the export with lua module with several functions to have more control on animations. It will have functions start, stop and play (start will create animation table and play it immediately). Also the animation itself have a bunch of parameters to play (like speed, callbacks, is_relative flag etc)

#### Animation Options

**is_relative**
All animation will be relative to initial node properties every time animation is started
Slice9 and Color properties can't relative, but they will skip initial node values setup


## Hotkeys

All hotkeys you can see in _Status Bar_ on hover mouse on button (not every button is supported)

- **F** - Center camera on selected node
- **Up/Down** - Select next or previous node
- **(CMD/CTRL) + Up/Down** - Change order of selected order
- **Left/Right** - Select next or previous animation key of current property
- **(CMD/CTRL) + R** - Set animation time to 0
- **(CMD/CTRL + SHIFT) + R** - Set animation time to the end
- **(CMD/CTRL) + S** - Save current project
- **(CMD/CTRL) + Z** - Undo action
- **(CMD/CTRL) + Y** - Redo action
- **(CMD/CTRL) + Shift + Z** - Undo action
- **(CMD/CTRL) + N** - Add new node
- **(CMD/CTRL) + D** - Delete selected node
- **(CMD/CTRL) + P** - Toggle parent mode for selected mode
- **P** - Open Node settings window
- **Space** - Play/Stop animation
