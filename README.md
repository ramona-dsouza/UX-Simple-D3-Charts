# UX-Simple-D3-Charts

## Overview

A minimal bar-chart visualization built with D3.js, focused on clear data encoding, predictable interaction feedback, and restrained motion. The project applies principles drawn from spatial and immersive (VR) data experiences—clarity at a glance, progressive disclosure, and consistent feedback—translated into a 2D web implementation.

**Live demo:** [Simple D3 Charts](https://ramona-dsouza.github.io/UX-Simple-D3-Charts/)

## Concept

Data visualization in immersive environments prioritizes legibility at distance, limited cognitive load, and explicit feedback on interaction. This project treats the browser as a constrained viewport and applies the same systems thinking: one primary chart, explicit axes, hover-revealed detail (tooltips), and animation used only to support understanding (staggered reveal) rather than decoration. The result is a single-view bar chart that communicates distribution quickly and reveals exact values on demand.

## Technical Architecture

- **Runtime:** D3.js v3 (script load, no build step).
- **Rendering:** SVG with a single root `<g>` for the chart, separate groups for vertical and horizontal axes.
- **Scales:** Linear scale for the quantitative axis (domain from 0 to data max); ordinal scale with `rangeBands` for bar placement and width.
- **Data:** In-memory array (e.g., 50 samples); can be replaced with any numeric series. No external data pipeline.
- **Styling:** Inline CSS for layout and typography (e.g., Josefin Sans); D3-driven attributes for fill, opacity, and tooltip positioning.
- **Dependencies:** None beyond D3 from the official CDN. No package manager required.

## Interaction Model

- **Initial load:** Bars animate from baseline upward with a staggered delay and elastic easing to convey sequence without overwhelming the user.
- **Hover:** Mouse over a bar shows a tooltip with the raw value and dims the bar (opacity 0.5); mouse out hides the tooltip and restores opacity. Cursor position drives tooltip placement.
- **No click or keyboard:** Interaction is intentionally limited to hover to keep the demo focused and to mirror “glance plus focus” behavior common in spatial UIs.

## Setup

1. Clone or download the repository.
2. Serve the project over HTTP (e.g., `npx serve`, or open `index.html` in a browser; some environments may restrict local file access for script/CDN).
3. Open the root URL in a modern browser. The chart renders immediately with sample data.

No build, environment variables, or backend required.

## Purpose

This project demonstrates:

- **Systems thinking:** Scales, axes, and data are kept in a single coherent pipeline; changes to data or dimensions propagate through domain/range and layout.
- **UX translation from spatial to web:** Principles from VR/spatial data viz (clarity, progressive disclosure, consistent feedback) are applied to a 2D, mouse-driven interface.
- **Technical implementation:** Direct use of D3's scale and axis APIs, SVG structure, and transition/easing.
