## Color Palette resource for Vice City Multiplayer (VC:MP)
A feature that allows the user to create a color palette on the client side.

### Setup
1. Clone the [repository](https://github.com/Razorn7/Color-Palette-for-Vice-City-Multiplayer/)
2. Copy the avaible folders such as `script/` and `sprites/` to your server `store/` folder.
3. Load and start the script using `dofile("colorPalette/main.nut")` in your main script file.
4. Path the events `GUI::ElementClick`, `GUI::ElementRelease` and `Script::ScriptProcess` to be like that:
- ```squirrel
  function GUI::ElementClick(element, mouseX, mouseY) {
    _colorPalette.functions.hookPaletteColorOnClick(element);
  }
  
- ```squirrel
  function GUI::ElementRelease(element, mouseX, mouseY) {
    _colorPalette.functions.hookPaletteColorOnRelease(element);
  }

- ```squirrel
  function Script::ScriptProcess() {
    _colorPalette.functions.processPalette();
  }
5. Have fun!

### Functions
- `GUIColorPalette()` - Used to create an GUI Element instance
  - `GUIColorPalette(VectorScreen Position, VectorScreen Size)`
  - `GUIColorPalette(VectorScreen Position, VectorScreen Size, Colour/RGBA BackgroundColor)`

### Events
- `GUI::ReceiveColorFromPalette(Colour/RGBA colour)` - This event is called when the user selects some color

### Example of usage
```squirrel
myColorPalette <- GUIColorPalette();
myColorPalette.Pos = VectorScreen(500, 400);
myColorPalette.Colour = Colour(0, 0, 0, 100);
myColorPalette.Size = VectorScreen(215, 150);
GUI.SetMouseEnabled(true);
```

### Screenshots
![Image 1](https://i.imgur.com/h9hd1Uk.png)
