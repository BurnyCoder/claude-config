# Plan: Rewrite WASD Movement to Gradual Acceleration Without Cap

## Overview

Rewrite the movement system so all WASD keys use gradual acceleration without any velocity cap, removing all other behaviors like friction or velocity resets.

## Current Behavior

In `player.js:280-305`:

- **W (Forward)**: Accumulates velocity using `acceleration * delta` with no cap. Velocity resets to 0 when key released.
- **S (Backward)**: Constant impulse using `moveSpeed * friction * delta` - does not accumulate
- **A/D (Strafe)**: Constant impulse using `moveSpeed * friction * delta` - does not accumulate

## Target Behavior

All WASD keys should:
1. Add to velocity using `acceleration * delta` each frame while held
2. No velocity cap - speed increases infinitely while key is held
3. No velocity reset when key released - velocity persists
4. No friction - velocity stays constant when no keys pressed

## File to Modify

**`player.js`**

## Changes

### 1. Simplify Movement Constants (lines 20-25)

Remove unused constants:
```javascript
// Movement settings
this.acceleration = 15.0;  // Acceleration rate for all movement
this.jumpForce = 8.0;
this.gravity = 20.0;
// Remove: moveSpeed, friction
```

### 2. Rewrite Movement Logic (lines 280-305)

Replace the entire movement handling section with:

```javascript
// Forward/Backward movement - gradual acceleration, no cap
if (this.moveForward) {
    this.velocity.x += direction.x * this.acceleration * delta;
    this.velocity.z += direction.z * this.acceleration * delta;
}
if (this.moveBackward) {
    this.velocity.x -= direction.x * this.acceleration * delta;
    this.velocity.z -= direction.z * this.acceleration * delta;
}

// Left/Right strafe - gradual acceleration, no cap
if (this.moveRight) {
    this.velocity.x += right.x * this.acceleration * delta;
    this.velocity.z += right.z * this.acceleration * delta;
}
if (this.moveLeft) {
    this.velocity.x -= right.x * this.acceleration * delta;
    this.velocity.z -= right.z * this.acceleration * delta;
}
```

This removes:
- The velocity reset when W is released (lines 284-291)
- The friction multiplier on S/A/D
- The different speed constant (`moveSpeed`) for S/A/D

## Verification

1. Run a local server: `python3 -m http.server 8000`
2. Open browser to `http://localhost:8000`
3. Test each key individually:
   - Hold W: velocity should continuously increase forward
   - Release W: velocity should NOT reset, player keeps moving
   - Hold S: velocity should continuously increase backward
   - Hold A: velocity should continuously increase left
   - Hold D: velocity should continuously increase right
4. Confirm there's no velocity cap by holding any direction for extended time
5. Confirm velocity persists when keys released (player slides indefinitely)
