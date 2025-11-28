# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Single-file HTML workout timer application for tendon rehabilitation exercises. Self-contained with embedded CSS and JavaScript - no build system, dependencies, or compilation required.

## Architecture

**Single HTML file (`index.html`):**
- Vanilla JavaScript timer system with state machine pattern
- Alternating left/right exercise intervals (30s work, 10s rest, 30s work, 80s rest)
- 5 rounds total
- Audio feedback using Web Audio API for interval transitions and countdown beeps
- Responsive design with mobile breakpoints

**State management:**
- `currentRound`, `currentStepIndex`, `timeRemaining` track progression through sequence
- `isRunning`, `isPaused` control timer state
- Skips final rest period on last round

**Timer sequence structure:**
```javascript
sequence = [
  { name: 'Left', duration: 30, class: 'left' },
  { name: 'Rest', duration: 10, class: 'rest' },
  { name: 'Right', duration: 30, class: 'right' },
  { name: 'Rest', duration: 80, class: 'rest' }
]
```

## Development

**Testing:** Open `index.html` directly in browser (no server required)

**Deployment:** Any static file hosting - single file to deploy

## Style Conventions

- Dark theme (#1a1a1a background)
- Color coding: blue (#4a9eff) for left, red (#ff6b6b) for right, green (#51cf66) for rest
- System font stack for native appearance
- Mobile-first responsive breakpoint at 480px
