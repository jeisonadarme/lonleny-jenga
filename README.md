# Jenga Game Simulation

An interactive 3D Jenga tower simulation built with Three.js and Cannon.js that automatically plays the game following strategic rules.

## Features

### Core Gameplay
- **3D Tower**: Starts with 14 levels, each containing 3 blocks in alternating orientations
- **Physics Simulation**: Realistic gravity and block interactions using Cannon.js
- **Automated Moves**: AI selects and removes blocks based on safety rules
- **Progressive Difficulty**: Adds a new layer every 3 successful moves
- **Game Over Detection**: Automatically collapses the tower when no safe moves remain

### Visual Features
- **Block Edges**: Black outlines for better visibility
- **Red Highlighting**: Selected block turns red before removal
- **Wood Texture**: Realistic material rendering with shadows
- **Dynamic Camera**: Orbit controls to view from any angle
- **Responsive Design**: Adapts to different screen sizes

### User Interface
- **Next Move Button**: Trigger the next move or skip current countdown
- **Reset Button**: Restart the game from scratch
- **Time Selector**: Choose countdown duration (5, 10, or 15 seconds)
- **Live Countdown**: Real-time display of remaining time in 0.1s precision
- **Move Counter**: Track total number of moves made
- **Status Messages**: Clear feedback about current game state

## Game Rules

The AI follows strategic Jenga rules to determine safe blocks:

### Block Configuration Patterns
- **xxx (3 blocks)**: Can remove left, right, or sometimes center (50% chance)
- **xxo (left + center)**: Only removes left block
- **oxx (center + right)**: Only removes right block
- **xox (left + right)**: No safe moves from this layer
- **Single blocks**: Not considered safe

### Safety Constraints
- Never removes blocks from the top layer
- Groups blocks by their vertical position (layer)
- Considers block orientation (even/odd layers are perpendicular)
- Uses position tolerance to handle physics-based shifts

## Technology Stack

- **Three.js**: 3D rendering and graphics
- **Cannon.js**: Physics engine for realistic simulations
- **OrbitControls**: Interactive camera movement
- **Vanilla JavaScript**: No framework dependencies

## How It Works

1. **Initialization**: Creates a 14-level tower with alternating block orientations
2. **Block Selection**: AI analyzes all layers (except top) to find safe blocks
3. **Highlighting**: Selected block turns red for the configured duration
4. **Removal**: Block is removed after countdown or immediately if skipped
5. **Progression**: Every 3 moves, a new layer is added to the top
6. **Game Over**: When no safe moves exist, tower collapses with physics simulation

## Controls

- **Left Click + Drag**: Rotate camera around tower
- **Scroll Wheel**: Zoom in/out
- **Next Move**: Execute next move or skip current countdown
- **Reset**: Clear tower and start fresh game
- **Time Dropdown**: Adjust countdown duration (5/10/15 seconds)

## Project Structure

```
jenga/
└── index.html          # Complete game implementation
    ├── CSS             # Styling and UI layout
    ├── Three.js Setup  # Scene, camera, renderer, lighting
    ├── Physics World   # Cannon.js integration
    ├── Block Class     # Individual block logic
    └── Game Class      # Main game logic and AI
```

## Key Classes

### `PhysicsWorld`
- Manages Cannon.js world and gravity
- Handles ground plane collision
- Updates physics simulation at 60 FPS

### `Renderer`
- Sets up Three.js scene and camera
- Configures lighting and shadows
- Manages OrbitControls
- Handles window resize events

### `Block`
- Creates Three.js mesh with geometry
- Adds edge outlines for visibility
- Syncs physics body with visual mesh
- Supports rotation for alternating layers

### `Game`
- Orchestrates overall gameplay
- Implements block selection AI
- Manages move countdown and timing
- Handles tower generation and collapse
- Controls UI updates and user interactions

## Future Enhancements

Potential improvements:
- Multiplayer mode
- Difficulty levels (stricter/looser rules)
- Sound effects
- Score tracking and leaderboards
- Manual block selection mode
- Save/load game state
- Tower stability metrics
- Animation speed controls
- Custom tower sizes

## Browser Compatibility

Works best in modern browsers with WebGL support:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## License

This is a personal project for educational and entertainment purposes.
