# Game Map Editor - 3D Block-Based Environment

## Overview
The **Game Map Editor** is a **3D block-based world editor** built using **Panda3D**. It allows users to create, modify, and navigate interactive 3D environments using various **block types, random map generation, and real-time editing tools**.

## Features
✔️ **3D Block Placement & Editing** – Users can place, modify, and remove blocks dynamically.
✔️ **Map Saving & Loading** – Save custom maps to disk and load them back for future editing.
✔️ **Random Map Generation** – Create procedurally generated maps.
✔️ **First-Person Camera Controls** – Move around the environment with smooth navigation.
✔️ **Collision Detection** – Prevents objects from overlapping.
✔️ **GUI-Based Editing Tools** (Future Feature).

## Installation
### Requirements
- **Python 3.9+**
- **Panda3D** (3D game engine)
- Additional dependencies:
  ```sh
  pip install panda3d
  ```
### Running the Editor
1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/game-map-editor.git
   ```
2. Navigate to the project directory:
   ```sh
   cd game-map-editor
   ```
3. Run the main script:
   ```sh
   python main.py
   ```

## Folder Structure
```
Game-Map-Editor/
│── main.py            # Entry point for the application
│── mapmanager.py      # Manages map generation, saving, and loading
│── editor.py          # Handles block editing and placement
│── controller.py      # Controls camera movement and input handling
│── block.py           # Defines block properties and rendering
│── assets/            # Stores textures and models
│── README.md          # Documentation
```
## Code Breakdown
### **1. Map Management (`mapmanager.py`)**
Handles block placement, saving/loading maps, and random map generation.
```python
class MapManager():
    def addBlock(self, position, color=None):
        """ Adds a new block to the world at a given position. """
        if color is None:
            color = getRandomColor()
        block = Block(position, color)
        self.blocks.append(block)
```
### **2. Block System (`block.py`)**
Defines how blocks are created, selected, and rendered in the 3D environment.
```python
class Block():
    def __init__(self, position, color):
        self.block = loader.loadModel('block')
        self.block.setPos(position)
        self.block.setColor(color)
        self.block.reparentTo(render)
```
### **3. Editor (`editor.py`)**
Handles real-time block selection, placement, and deletion.
```python
class Editor(DirectObject):
    def addBlock(self):
        """ Adds a block at the selected position. """
        if self.new_position:
            self.map_manager.addBlock(self.new_position)
```


## Author
Developed by **Sofiya Dassayeva**.
