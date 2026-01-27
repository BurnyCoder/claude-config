# Simplest Minecraft Clone - Implementation Plan

## Overview
Create a minimal viable Minecraft clone using **Three.js** for 3D rendering and **Vite** as build tool.

## File Structure
```
/home/burny/vibecodingfun/game/1/
├── index.html              # Entry point with click-to-play overlay
├── package.json            # Dependencies (three, vite)
├── style.css               # Fullscreen canvas styling
└── src/
    ├── main.js             # Three.js scene, game loop
    ├── World.js            # Voxel world management
    ├── Player.js           # First-person controls + raycasting
    └── BlockTypes.js       # Block definitions (grass, dirt, stone)
```

## Features (Minimal Scope)
- 16x16 flat voxel world (4 layers: stone, dirt x2, grass)
- First-person camera with PointerLockControls
- WASD movement + mouse look
- Left-click to break blocks, right-click to place
- 3 block types: Grass, Dirt, Stone (keys 1-3 to select)
- Colored materials (no textures - simplest approach)

## Implementation Steps

### Phase 1: Project Setup
1. `npm init -y`
2. `npm install three`
3. `npm install -D vite`
4. Create index.html, style.css, package.json scripts

### Phase 2: Basic Three.js Scene (src/main.js)
1. Initialize scene, camera, renderer
2. Add ambient + directional lighting
3. Set sky color background
4. Create game loop with requestAnimationFrame

### Phase 3: Block System (src/BlockTypes.js, src/World.js)
1. Define BlockTypes enum (AIR, GRASS, DIRT, STONE)
2. Create colored MeshLambertMaterial for each type
3. World class with Map storage (key: "x,y,z")
4. setBlock(), removeBlock(), getBlock() methods
5. Each block = individual BoxGeometry mesh

### Phase 4: World Generation
1. generateFlatWorld(16, 16) in World.js
2. Layer structure: stone(y=0), dirt(y=1-2), grass(y=3)

### Phase 5: Player Controls (src/Player.js)
1. PointerLockControls for mouse look
2. Click-to-play overlay activates pointer lock
3. WASD keyboard tracking
4. Movement using controls.moveForward/moveRight
5. Simple floor collision (y >= player height)

### Phase 6: Block Interaction
1. Raycaster from camera center
2. Crosshair div in center of screen
3. Left-click: remove intersected block
4. Right-click: place block using hit.point + face.normal
5. Keys 1-3 select current block type

## Key Technical Decisions
- **Individual meshes per block**: Simplest to implement, OK for small world
- **Map with "x,y,z" keys**: Simple O(1) block lookup
- **No textures**: Use solid colors for MVP
- **No full collision**: Only floor collision, can walk through blocks
- **No inventory UI**: Number keys select block type directly

## Dependencies
```json
{
  "dependencies": { "three": "^0.160.0" },
  "devDependencies": { "vite": "^5.0.0" }
}
```

## Verification
1. Run `npm run dev` to start Vite dev server
2. Open browser at localhost:5173
3. Click to lock pointer
4. WASD to move, mouse to look
5. Left-click blocks to remove them
6. Press 1/2/3, right-click to place different blocks

## Sources
- [Three.js PointerLockControls](https://threejs.org/docs/examples/en/controls/PointerLockControls.html)
- [minecraft-threejs-clone](https://github.com/dgreenheck/minecraft-threejs-clone)
- [freeCodeCamp Minecraft Tutorial](https://www.freecodecamp.org/news/code-a-minecraft-clone-using-react-and-three-js/)
