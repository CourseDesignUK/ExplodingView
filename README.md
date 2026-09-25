Markdown
# Dräger PSS 7000 SCBA 3D Exploded Viewer

A web-based, interactive 3D visualization tool for the Dräger PSS 7000 Self-Contained Breathing Apparatus. Built with Three.js, this application provides an animated exploded assembly view with interactive component inspection.

## Core Features

*   **Draco-Compressed GLTF Loading:** Asynchronous loading of `.glb` assets utilizing the Three.js `GLTFLoader` and `DRACOLoader`.
*   **Interactive Exploded View:** Linear interpolation of component positions driven by a UI slider and dedicated assemble/explode trigger buttons.
*   **Raycast Selection:** Hover-based mesh intersection detection to trigger context-specific data panels (Part Number, Material, Specification, Standard).
*   **Dynamic UI Annotations:** 2D HTML badges anchored to 3D local geometric centers. Leader lines are drawn via HTML Canvas with deadband hysteresis to prevent rapid side-switching artifacts.
*   **Material Overrides:** Automatic detection and application of `MeshPhysicalMaterial` for transparent components (e.g., polycarbonate mask visors).
*   **Auto-Framing:** Bounding-box calculation upon load completion to normalize scale and set optimal camera distance.

## Project Structure

Ensure the following files are located in the same directory. The application requires all four `.glb` files to initialize the render loop.

```text
├── index.html
├── body.glb    (Chassis & Reducer Harness)
├── mask.glb    (FPS 7000 Full Face Mask)
├── tank.glb    (Compressed-Air Cylinder)
└── unit.glb    (Bodyguard 7000 Telemetry Unit)
