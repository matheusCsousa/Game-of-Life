# Conway's Game of Life — Raylib

C++ implementation of [Conway's Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life) using [raylib](https://www.raylib.com/) for rendering.

![preview](screenshots/gameoflife.png)

## Controls

| Input | Action |
|---|---|
| `Space` | Play / Pause |
| `Left Click` | Toggle cell alive/dead |

Background turns darker when paused.

## Rules

Each cell follows the classic Conway rules per generation:

- **Live cell**: survives with 2 or 3 neighbors, dies otherwise
- **Dead cell**: becomes alive with exactly 3 neighbors

## Build

Requires raylib installed as a static library (`libraylib.a`).

```bash
cmake -B build
cmake --build build
./build/build
```

On Arch/Manjaro:
```bash
sudo pacman -S raylib cmake
```

## Project Structure

```
.
├── src/
│   ├── main.cpp
│   ├── grid/
│   │   ├── grid.hpp        # Grid data structure
│   │   └── grid.cpp
│   └── simulation/
│       ├── simulation.hpp  # Simulation logic + neighbor counting
│       └── simulation.cpp
├── screenshots/
└── CMakeLists.txt
```

## Config

Hardcoded in `main.cpp`:

| Parameter | Value |
|---|---|
| Window size | 750×750 |
| Cell size | 25px |
| Grid | 30×30 |
| FPS | 12 |
