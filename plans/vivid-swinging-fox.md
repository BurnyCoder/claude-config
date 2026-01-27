# Performance Optimization Plan

## Problem
Severe lag after implementing gradual chunk generation. Root causes identified:

1. **Per-block meshes**: 160,000+ individual mesh objects in scene
2. **Excessive edge rebuilding**: 16,640 mesh updates per chunk generation
3. **Queue sorting every frame**: O(n log n) even when unchanged
4. **String parsing in update loop**: Parsing chunk keys every frame
5. **Expensive distance checks**: Using sqrt instead of squared distance

## Optimization Strategy

### Priority 1: Reduce Edge Rebuilding (Quick Win)
**File:** `world.js`

**Changes:**
- Only rebuild the specific edge facing the new chunk (not all 4 edges)
- Skip rebuilding blocks that have no neighbors in the new chunk
- Reduce from 4,160 updates to ~260 per neighbor

```javascript
// Instead of rebuilding ALL edges, only rebuild the edge facing the new chunk
rebuildChunkEdge(cx, cz, direction) // 'north', 'south', 'east', 'west'
```

### Priority 2: Optimize Update Loop (Quick Win)
**File:** `world.js`

**Changes:**
- Only sort queue when items are added (not every frame)
- Use squared distance (avoid sqrt)
- Cache chunk coordinates instead of parsing strings

```javascript
// Before: expensive every frame
this.chunkQueue.sort((a, b) => a.dist - b.dist);
const dist = Math.sqrt(dx * dx + dz * dz);

// After: only when needed
if (this.queueDirty) { this.chunkQueue.sort(...); this.queueDirty = false; }
const distSq = dx * dx + dz * dz;
if (distSq > this.unloadDistanceSq) { ... }
```

### Priority 3: Reduce Chunks Per Frame During Fast Movement
**File:** `world.js`

**Changes:**
- Set `chunksPerFrame = 1` (already set, verify it's working)
- Add frame budget: skip chunk gen if frame took too long
- Increase unload distance to reduce churn

### Priority 4: Limit Raycast Scope (Medium Effort)
**File:** `player.js`

**Changes:**
- Only raycast against meshes within reach distance
- Filter meshes by player position before raycasting

```javascript
const nearbyMeshes = meshes.filter(m =>
    m.position.distanceToSquared(this.camera.position) < 36 // 6 block radius squared
);
```

## Files to Modify

| File | Changes |
|------|---------|
| `world.js` | Optimize rebuildChunkEdges, update loop, queue sorting |
| `player.js` | Filter raycast meshes by distance |

## Verification

1. Run game, move around quickly
2. Verify no stuttering when chunks load
3. Check console for mesh/block counts
4. Test block placing/removing still works
5. Verify terrain still generates correctly at chunk boundaries
