# Custom WorldEdit Skript

A Skript-based, simplified version of basic [WorldEdit](https://enginehub.org/worldedit) tools for Minecraft servers. This script lets you select regions, fill, replace, or build spheres with easy commands, using a stone shovel as your "wand" item. Permissions are required for access to each function.

---

## Features

- **Wand Tool:**  
  - Right-click with a stone shovel named `&7Wand` to set point 2.
  - Left-click to set point 1.
  - Use `//wand` to obtain your wand.
- **Region Commands:**  
  - `//set <block>`: Fills the region with the specified block type(s).
  - `//replace <old> <new>` or `//repl <old> <new>`: Replace a block type in the region.
  - `//walls <block>`: Create walls around a selected region.
  - `//cut`: Remove and copy the region (fill with air).
  - `//paste`: Paste the copied or cut region at your location.
  - `//pos1`, `//pos2`: Set points by your own position, useful for quick selection.
- **Shape Tools:**
  - `//sphere <radius> <block>`: Creates a filled sphere around you.
- **Movement:**
  - `/up <n>`: Teleports you up by *n* blocks and places glass under you.
  
## Permissions

| Command         | Permissions              |
|-----------------|-------------------------|
| //wand          | worldedit.admin OR worldedit.wand  |
| //set           | worldedit.admin OR worldedit.set   |
| //replace/repl  | worldedit.admin OR worldedit.replace|
| //walls         | worldedit.admin OR worldedit.walls |
| //sphere        | worldedit.admin OR worldedit.sphere|
| //cut           | worldedit.admin OR worldedit.cut   |
| //paste         | worldedit.admin                   |
| //pos1, //pos2  | worldedit.admin OR worldedit.pos  |
| /up <n>         | worldedit.admin OR worldedit.up   |

## Usage Examples

### Get the Wand
```
//wand
```
> Gives you a stone shovel named `&7Wand`. Use this item to select points (by right/left clicking blocks).

### Select Positions
- **Left Click:** Sets **Point 1**.
- **Right Click:** Sets **Point 2**.

Or, use:
```
//pos1     # Sets Point 1 to your position
//pos2     # Sets Point 2 to your position
```

### Fill a Region
```
//set stone
```

### Replace Within the Region
```
//replace dirt
//repl cobblestone
```

### Create Region Walls
```
//walls cobblestone
```

### Cut/Copy and Paste
```
//cut
//paste
```

### Build a Sphere
```
//sphere 5 glass
```
> Builds a glass sphere of radius 5 centered at your position and moves you up inside the sphere.

### Upwards Movement
```
/up 10
```
> Teleports you up 10 blocks and puts glass beneath your feet.

## Tab Completion

Many commands support tab completion for available block types and standard dimensions for spheres and `/up`.

## Region Variable Reset

All region point variables reset on (server) script reload to ensure old regions are cleared.

## Notes

- Points are stored **per player** and tracked using variables like `{x1.%player%}`.
- Messages and actions occur only if the command sender has the required permission(s).
- Commands attempt to use efficient methods for fill operations (ticker/double layer for large y-differences).
- The script hooks into Skript's event system, so is meant for Skript-enabled Minecraft servers.
- **Test thoroughly before using on a live server!** This is a powerful building tool and can impact large areas.

---

### Requirements

- [Skript](https://docs.skunity.com/)
- Perm plugin
---

## Credits

Script by harmfulladvocado
Inspired by WorldEdit

---
```
