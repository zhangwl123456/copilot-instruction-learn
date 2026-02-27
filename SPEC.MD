# Simple Tetris Spec

## Overview
Build a minimal, playable Tetris clone that runs in the browser using plain HTML, CSS, and JavaScript. Keep the implementation simple and focused on core gameplay.

## Goals
- Playable game loop with falling tetrominoes.
- Line clear and basic scoring with an on-screen score display.
- Keyboard controls using arrow keys and Space for hard drop.
- Simple visuals and UI.
- Provide a restart button with confirmation.

## Non-Goals
- No hold piece.
- No next-piece preview.
- No sound, levels, or advanced effects.

## User Experience
- The game renders in a single page with a visible grid and score.
- A restart button sits under the score and asks for confirmation before resetting.
- Controls:
  - Left/Right: move piece.
  - Down: soft drop.
  - Up: rotate.
  - Space: hard drop.
- The game ends when a new piece cannot spawn.

## Game Rules
- Standard 7 tetrominoes (I, O, T, S, Z, J, L).
- Rotation: simple clockwise rotation.
- Line clear: remove completed rows and shift above rows down.
- Scoring: +1 per cleared line.

## Rendering
- Use a fixed-size grid (10x20).
- Each cell is a square block in a CSS-styled grid or canvas.
- Use distinct colors per tetromino for readability.

## Technical Plan
- Single HTML file with embedded CSS and JS or separate files (TBD).
- Use a 2D array for the board state.
- Maintain current piece state (shape matrix, position, color).
- Main loop via `setInterval` for gravity; allow manual moves between ticks.
- Collision detection for walls and existing blocks.
- Lock piece when it cannot move down; then clear lines and spawn a new piece.

## Acceptance Criteria
- Game is playable with listed controls.
- Lines clear and score increments correctly.
- Game over triggers when spawn is blocked.
- Restart button resets board and score after confirmation.
- Runs by opening the HTML file in a browser.
