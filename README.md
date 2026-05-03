# Upsetting Process — Stress & Power Analyzer

An interactive web-based tool for analyzing stress states, strain rates, and power balance in metal forming processes (upsetting/forging).

## Features

- **Interactive 3D Visualization**: Free body diagram with stress tensors and shear components
- **Real-time Analysis**: Instant computation of stress invariants, principal stresses, Mohr's circles
- **Velocity Field Computation**: Linear velocity field with friction shear effects
- **Power Balance**: External, internal, and upper bound power calculations
- **Multiple Test Cases**: Q1 (20×20×50), Q2 (8×4×2) with various boundary conditions
- **Export Options**: JSON, YAML, Markdown, and plain text outputs
- **Axis-Agnostic**: Supports loading along X, Y, or Z directions
- **Boundary Conditions**: Fixed bottom or free both ends

## Quick Start

Simply open `index.html` in a browser, or deploy to Vercel for online access.

## Input Parameters

- Workpiece dimensions (Length × Width × Height)
- Normal stress magnitude and direction (X, Y, or Z)
- Ram velocity
- Shear stresses (τ_xy, τ_yz, τ_zx)
- Boundary condition (fixed or free)

## Output Sections

1. Applied stress tensor
2. Stress invariants (I₁, I₂, I₃)
3. Principal stresses & deviatoric tensor
4. Mohr's circle
5. Flow condition (Von Mises & Tresca)
6. Strain rate tensor
7. Velocity field equations
8. Velocities at coordinates
9. External power (compression + shear)
10. Internal power
11. Principal stress × strain rate
12. Equivalent stress & effective strain
13. Upper bound power

## Technology Stack

- Pure HTML/CSS/JavaScript (no build required)
- Three.js for 3D visualization
- KaTeX for mathematical rendering
- Responsive design with warm color theme

## Deployment

### Vercel (Recommended)

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

Or connect your GitHub repository to Vercel for automatic deployments.

### Static Hosting

Any static file server will work - just serve the directory containing `index.html`.

## License

Educational use - Indian Institute of Space Science and Technology (IIST)
