# Orbital Velocity

A top-down spaceflight experiment built around thrust, gravity, and orbital motion.

[Open project](https://actiondaveinri.github.io/orbital-velocity/) · [All projects](https://actiondaveinri.github.io/spaceship/)

The repository root is this single project’s directory. `index.html` is unchanged. A working graphics screenshot is pending: this capture browser lacks the WebGL context requested by the game. Gameplay has not been revalidated.

## Original project notes and notices

# Orbital Velocity

**Escape Velocity-Inspired Space Game with Orbital Mechanics**

A top-down space game where you pilot a ship through a planetary system, experiencing realistic orbital mechanics. Navigate using Newtonian physics, enter stable orbits around planets, and explore the gravity wells of multiple celestial bodies.

## Gameplay

### Core Mechanics

1. **Launch** your ship into the planetary system
2. **Navigate** using Newtonian physics with thrust controls
3. **Enter Orbits** around planets by matching velocity and distance
4. **Explore** multiple planets with different masses and sizes
5. **Experience Gravity** as planets pull your ship naturally

### Controls

- **WASD / Arrow Keys**: Thrust and rotate your ship
  - **W / Up Arrow**: Thrust forward
  - **A / Left Arrow**: Rotate left
  - **D / Right Arrow**: Rotate right
  - **S / Down Arrow**: Reverse thrust
- **Mouse**: Aim weapons
- **Space**: Fire weapon

### Systems

#### Ship Physics
- **Newtonian Movement**: Momentum-based physics with minimal damping
- **Independent Rotation**: Rotate and thrust independently
- **Power Management**: Thrusting and weapons drain power; regenerates when idle
- **Gravity Interaction**: Ships are affected by planetary gravity

#### Orbital Mechanics
- **Gravity Wells**: Planets exert gravitational force based on inverse square law
- **Stable Orbits**: Ships naturally enter orbits when:
  - Velocity is roughly perpendicular to planet
  - Speed matches orbital velocity for the distance
  - Distance is within orbital range (50-500 km)
- **Orbital Detection**: UI indicates when ship is in stable orbit
- **Visual Feedback**: Orbit indicators show when orbiting

#### Planet System
- **Multiple Planets**: Three planets with different masses and sizes
- **Gravity Visualization**: Gravity wells shown as concentric circles
- **Collision Detection**: Ships bounce off planets if they get too close
- **Orbital Velocity**: Each planet has different orbital velocities at different distances

#### Power Core
- Shared resource pool (0-100)
- Drains when using:
  - Thrusters: 0.3 per frame
  - Weapons: 5 per shot
- Regenerates 0.15 per frame when idle

## Technical Details

### Physics Constants
- **Gravity Constant**: 0.5 (simplified for gameplay)
- **Thrust Force**: 0.15 units/frame
- **Rotation Speed**: 0.1 radians/frame
- **Damping**: 0.995 per frame (minimal for orbital mechanics)
- **Max Speed**: 10 units/frame
- **Orbit Range**: 50-500 km from planet surface

### Orbital Mechanics

The game uses simplified orbital mechanics:

1. **Gravity Calculation**: `F = G * (m1 * m2) / r^2`
   - Applied as acceleration to ship velocity
   - Multiple planets affect ship simultaneously

2. **Orbital Velocity**: `v = sqrt(G * M / r)`
   - Calculated for each planet at different distances
   - Ships enter orbit when velocity matches this value

3. **Orbit Detection**:
   - Checks if velocity is perpendicular to planet (dot product < 0.3)
   - Verifies speed is within 30% of orbital velocity
   - Confirms distance is within orbital range

### Game Balance
- Initial Power: 100
- Initial Health: 100
- Weapon Cooldown: 200ms
- Projectile Lifetime: 120 frames

## Development

Built as a standalone HTML5 Canvas game. No dependencies required - just open `index.html` in a modern web browser.

### Features Implemented
- ✅ Planet system with gravity
- ✅ Newtonian ship physics
- ✅ Orbital mechanics detection
- ✅ Gravity visualization
- ✅ Camera system following ship
- ✅ Power management system
- ✅ Weapon system with gravity-affected projectiles
- ✅ UI with speed, altitude, and orbit status
- ✅ Multiple planets with different properties

## License

2025 David Miles Santagata - GPL 4 Non Commercial License

This work is protected IP, but you may use it for non-commercial purposes. You may even modify it for non-commercial purposes. However, if any of this code ends up in a commercial product I'll sue your pants off. Have fun :)


