# POINT ARCHITECT

**Game 808**

Point Architect is an original tactical tennis strategy game inspired by the intelligent, composed style of professional tennis player **Emma Navarro**.

Rather than treating tennis as a reflex-only sports game, Point Architect focuses on the decisions that build a point: court position, shot selection, geometry, opponent displacement, risk, pressure, stamina, and changing match conditions.

The central question is simple:

> **Can you construct the point before trying to finish it?**

---

## Current Prototype

The current prototype is a browser-based tactical tennis simulation.

The human player controls the on-court agent:

**X**

The computer-controlled opponent is:

**Y**

Emma Navarro is the featured inspiration and presentation identity for X, while the underlying simulation remains deliberately separated into generic **X/Y game-state variables**.

This allows the tennis engine to remain reusable for future players, opponents, tournaments, scenarios, and game modes.

---

## Core Gameplay

Each rally is treated as a changing tactical state.

The player:

1. Reads the incoming ball.
2. Evaluates court position.
3. Chooses a tactical shot.
4. Selects a target area.
5. Resolves trajectory, risk, movement, and opponent response.
6. Receives an updated tactical situation.
7. Continues constructing the point until one player wins it.

Every shot should influence what happens next.

The game is not designed around a simple:

**GOOD SHOT / BAD SHOT**

model.

Instead, a shot can:

- Move the opponent
- Improve court position
- Create an attack ball
- Reduce opponent recovery time
- Increase error exposure
- Force defense
- Open the court
- Create a winner opportunity
- Produce a forced error
- Produce an unforced error

---

## Tactical Shot System

Current prototype shot choices include:

- Heavy Crosscourt
- Down-the-Line Attack
- Inside-Out Forehand
- Defensive Reset
- Drop Shot
- Short-Angle Attack
- Approach Shot
- Lob

Current target zones:

- Left
- Middle
- Right

Serve choices:

- Wide
- Body
- T

Future versions can expand shot selection to include slice, volleys, passing shots, kick serves, flat serves, return styles, overheads, and additional directional targets.

---

## Pressure Index

Point Architect includes a live **Pressure Index**.

The Pressure Index estimates how much tactical control X currently has over the rally.

It is influenced by factors including:

- Court position
- Opponent displacement
- Shot quality
- Attack opportunity
- Rally context
- Error exposure
- Match pressure

The exact weighting is intentionally still experimental and will be tuned through playtesting.

---

## Tennis Physics

The game currently uses a lightweight analytical tennis model rather than a full rigid-body physics engine.

The simulation considers:

- Ball pace
- Direction
- Depth
- Spin
- Wind
- Shot risk
- Player movement
- Opponent travel distance
- Recovery position
- Stamina
- Reach difficulty

The goal is not to reproduce every microscopic racquet and ball interaction.

The physics exists to create believable **tactical consequences**.

For example:

**Heavy crosscourt forehand → opponent displacement → weaker recovery position → increased Pressure Index → attack opportunity**

---

## Match Structure

The prototype currently uses short-form tennis scoring:

- Standard point scoring
- Games
- First to 4 games
- Tiebreak at 3–3

Longer formats may later include:

- Full sets
- Best-of-three matches
- Tournament formats
- Career progression
- Daily tactical challenges

---

## Environment

Current prototype:

- Hard court
- Basic wind model

Planned environmental variables include:

- Clay
- Grass
- Court speed
- Bounce characteristics
- Wind direction
- Wind speed
- Temperature
- Humidity
- Altitude
- Indoor / outdoor conditions

Environmental conditions should change strategy without overwhelming the tennis itself.

---

## Opponent AI

The current Y opponent uses a lightweight tactical response system.

Long-term opponent behavior may consider:

- Repeated X patterns
- Preferred shot directions
- Serve tendencies
- Return tendencies
- Rally length
- Score pressure
- Surface
- Court position
- Previous successful tactics
- Previous failed tactics

The long-term objective is adaptive opposition.

Repeatedly using the same successful strategy should gradually become less effective as the opponent adjusts.

---

## Long-Term Vision

Point Architect is intended to grow into a reusable tactical tennis simulation engine.

Potential future systems include:

- Multiple opponent archetypes
- Adaptive AI
- Clay, grass, and varied hard courts
- Tournament campaign
- Player scouting
- Match preparation
- Career statistics
- Serve placement control
- Return anticipation
- Tactical grading
- Environmental simulation
- Daily challenges
- Global tennis locations
- Scenario editor
- Player-specific tactical profiles

Potential campaign destinations include Charleston, Madrid, Rome, Roland Garros, Wimbledon, Montréal, Cincinnati, and New York.

---

## Design Philosophy

Point Architect should never become a generic tennis game with different artwork attached to it.

The defining mechanic is:

> **TACTICAL POINT CONSTRUCTION**

The player should be rewarded for:

- Creating space
- Manipulating geometry
- Moving the opponent
- Recognizing attack opportunities
- Defending intelligently
- Varying patterns
- Managing risk
- Responding to pressure
- Finishing efficiently

Winning the point matters.

Understanding **why the point was won** matters too.

---

## Technical Architecture

The prototype currently runs as a standalone browser game using:

- HTML
- CSS
- JavaScript
- Canvas

No C++ or external physics engine is required for the current simulation.

The underlying game model uses generic internal identities:

- `X` — human-controlled player
- `Y` — AI opponent

This separation is intentional.

Future integration into the main Games platform may split the simulation into modules such as:

```text
PointArchitect.tsx
tennisPhysics.ts
pointState.ts
opponentAI.ts
scoring.ts
environment.ts
```

The current priority is validating the gameplay loop before increasing architectural complexity.

---

## Running the Prototype

The standalone prototype does not require a build process.

Open:

```text
index.html
```

in a modern browser.

For local development inside the main Games platform, Point Architect will eventually be integrated into the existing React / TypeScript / Vite application.

---

## Development Status

Current stage:

**Early playable prototype / active playtesting**

Implemented:

- Overhead tennis court
- X vs Y
- Tactical shot selection
- Target selection
- Serve selection
- Ball trajectory visualization
- Player positioning
- Opponent displacement
- Wind
- Stamina
- Pressure Index
- Tennis point scoring
- Game scoring
- Short-form match structure
- Tiebreak support

Still experimental:

- Shot probabilities
- Physics coefficients
- AI intelligence
- Pressure Index weighting
- Stamina model
- Court positioning
- Match balance
- Environmental effects

---

## Emma Navarro Inspiration

Point Architect was conceived as an original tennis strategy game inspired by **Emma Navarro** and the tactical qualities associated with high-level professional tennis.

The project is interested in tennis intelligence: point construction, composure, positioning, pressure management, efficient movement, and choosing the right shot at the right moment.

Emma Navarro serves as the creative inspiration for the featured player presentation.

The simulation engine itself remains generic and reusable.

---

## Licensing & Attribution Notice

Point Architect is an independent, unofficial tennis strategy project.

It is not affiliated with, sponsored by, authorized by, or endorsed by Emma Navarro, the WTA, USTA, ITF, any Grand Slam tournament, or their respective sponsors.

Emma Navarro's name and likeness, where used, identify the real-world athlete depicted and do not imply participation in or endorsement of the project.

All third-party names, trademarks, tournament names, logos, photographs, and other intellectual property remain the property of their respective owners.

Photographic and other third-party media should be included in publicly distributed versions only where the project has the appropriate permission, license, or other lawful basis for use.

Development or reference imagery that has not been cleared for public use should remain limited to internal development and private playtesting.

---

## Current Internal Rule

Before expanding the game into a large tournament or career simulation, the project must answer one question:

> **Can we make one rally worth thinking about?**

If the answer is yes, everything else can grow from there.

---

## Project

**Title:** Point Architect  
**Game Number:** 808  
**Genre:** Tactical Tennis Strategy / Simulation  
**Human Agent:** X  
**AI Agent:** Y  
**Featured Inspiration:** Emma Navarro  
**Core Mechanic:** Tactical Point Construction  
**Signature Metric:** Pressure Index  

---

## Status

**Prototype in active development.**

Expect mechanics, balance, presentation, physics, AI behavior, terminology, and game structure to change substantially during playtesting.
