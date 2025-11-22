# 3D Jenga Game

A browser-based 3D Jenga game built with **Three.js** and **Cannon-es**.

## Features

-   **Realistic 3D Graphics**: Rendered using Three.js with realistic wood textures and lighting.
-   **Automated Gameplay**: The "Next Move" button automatically selects a safe block to remove based on Jenga rules.
-   **Dynamic Progression**: The tower grows! A new layer of blocks is added to the top every 3 moves.
-   **Reset Functionality**: Easily restart the game at any time.
-   **Interactive Camera**: Fully controllable camera (OrbitControls) to view the tower from any angle.

## How to Run

1.  Ensure you have the `index.html` and `wood.jpg` files in the same directory.
2.  Simply open `index.html` in any modern web browser.
3.  No server or installation required!

## Controls

-   **Next Move Button**: Click to have the computer find and remove a safe block.
-   **Reset Button**: Click to reset the tower and start over.
-   **Camera Controls**:
    -   **Left Click + Drag**: Rotate the view.
    -   **Right Click + Drag**: Pan the view.
    -   **Scroll**: Zoom in and out.

## Technologies Used

-   [Three.js](https://threejs.org/) - 3D Library
-   [Cannon-es](https://github.com/pmndrs/cannon-es) - Physics Engine
