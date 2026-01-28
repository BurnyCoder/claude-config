# Plan: Infinite World Generation

## Overview
Transform the finite 128x128 world into an infinite procedurally generated world with dynamic chunk loading/unloading based on player position.

## Files to Modify

### 1. world.js (main changes)
### 2. main.js (game loop integration)
### 3. player.js (no changes needed - verify compatibility)

---

## Implementation Steps

### Step 1: Add New Constants and Data Structures (world.js)

**Remove:**
- `this.worldWidth = 128`
- `this.worldDepth = 128`

**Add:**
```javascript
const RENDER_DISTANCE = 8;    // Chunks around player (128 blocks radius)
const UNLOAD_DISTANCE = 10;   // Distance before unloading

// In constructor:
this.loadedChunks = new Set();      // Loaded chunk columns ("cx,cz")
this.generatedChunks = new Set();   // Generated terrain columns
```

### Step 2: Add Chunk Column Helpers (world.js)

```javascript
getChunkColumnKey(x, z) { ... }     // Returns "cx,cz" for 2D column
parseChunkColumnKey(key) { ... }    // Returns { cx, cz }
seededRandom(x, z) { ... }          // Deterministic random for trees
```

### Step 3: Refactor Terrain Generation (world.js)

**Replace** `generateTerrain()` with:

1. `generateChunkColumn(cx, cz)` - Generate terrain for one 16x16 column
   - Same noise algorithm, scoped to chunk bounds
   - Trees only inside chunk (avoid edges)
   - Uses seeded random instead of Math.random()

2. `generateTerrain()` - Initial load only
   - Loads chunks around spawn point
   - Uses render distance circle

### Step 4: Add Chunk Loading System (world.js)

```javascript
loadChunkColumn(cx, cz) {
    // Skip if already loaded
    // Generate terrain if needed
    // Build meshes for vertical chunks
    // Add to loadedChunks
}

unloadChunkColumn(cx, cz) {
    // Remove meshes from scene
    // Dispose geometries
    // Remove from loadedChunks
}

updateChunks(playerX, playerZ) {
    // Calculate player's chunk position
    // Load chunks within RENDER_DISTANCE (closest first, max 2/frame)
    // Unload chunks beyond UNLOAD_DISTANCE
}
```

### Step 5: Update getBlock() for Safety (world.js)

Modify `getBlock()` to generate chunk on-demand if accessed before loading:
```javascript
getBlock(x, y, z) {
    const block = this.blocks.get(key);
    if (block !== undefined) return block;

    // Generate chunk if not generated yet
    if (!this.generatedChunks.has(columnKey)) {
        this.generateChunkColumn(cx, cz);
        return this.blocks.get(key) || BlockType.AIR;
    }
    return BlockType.AIR;
}
```

### Step 6: Update Game Loop (main.js)

Add chunk update in `animate()`:
```javascript
animate() {
    // ... existing player update

    this.world.updateChunks(
        this.player.position.x,
        this.player.position.z
    );

    // ... render
}
```

### Step 7: Adjust Fog and Camera (main.js)

Update fog to match render distance:
```javascript
const fogNear = RENDER_DISTANCE * 16 * 0.6;  // ~77 blocks
const fogFar = RENDER_DISTANCE * 16;         // ~128 blocks
this.scene.fog = new THREE.Fog(0x87CEEB, fogNear, fogFar);
```

---

## Key Design Decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| Chunk loading throttle | 2 chunks/frame | Prevents stuttering |
| Render distance | 8 chunks | Same as original 128 block world |
| Block data retention | Keep generated data | Allows fast revisits |
| Tree placement | Seeded random | Deterministic across reloads |

---

## Verification

1. **Test spawn**: Player spawns on solid ground
2. **Test exploration**: Walk in any direction, new terrain generates
3. **Test return**: Walk back, previously visited terrain remains
4. **Test performance**: Maintain 60fps during exploration
5. **Test collision**: No falling through unloaded chunks
6. **Test block placement**: Works in newly generated chunks

Run with: `python3 -m http.server 8000` then open `http://localhost:8000`
