# Conway's Game of Life Implementation in Python 2

This project implements Conway's Game of Life, a classic cellular automaton, using Python 2. The visualization is handled by the `graphics.py` library, which must be in the same directory as the project files. The project allows users to observe the evolution of various patterns on a grid-based board through both simulation and animation.

## Problem Definition

Conway's Game of Life is a zero-player game that consists of a grid of cells, each of which can be either alive or dead. The state of each cell in the next generation is determined by the current state of its neighbors according to the following rules:

1. Any live cell with fewer than two live neighbors dies (underpopulation).
2. Any live cell with two or three live neighbors lives on to the next generation (survival).
3. Any live cell with more than three live neighbors dies (overpopulation).
4. Any dead cell with exactly three live neighbors becomes a live cell (reproduction).

The game simulates the evolution of the cells over multiple generations, starting from an initial configuration.

## Implementation Details

The project is organized into the following components:

### Block Class

The `Block` class represents each cell in the grid. Key attributes and methods include:
- **Attributes**: 
  - `x` and `y`: Grid coordinates of the block.
  - `status`: Indicates whether the block is 'alive' or 'dead'.
  - `new_status`: The status to be updated in the next generation.
- **Methods**:
  - `set_live(canvas)`: Marks the block as alive and draws it on the canvas.
  - `set_dead()`: Marks the block as dead and removes it from the canvas.
  - `is_live()`: Returns whether the block is currently alive.
  - `reset_status(canvas)`: Updates the block's status for the next generation.

### Board Class

The `Board` class manages the grid and the blocks within it. Key attributes and methods include:
- **Attributes**: 
  - `width` and `height`: Dimensions of the board in grid units.
  - `canvas`: The drawing area for visualizing the blocks.
  - `block_list`: A dictionary that maps coordinates to `Block` objects.
- **Methods**:
  - `random_seed(percentage)`: Randomly activates a percentage of the blocks on the board.
  - `seed(block_coords)`: Activates blocks at specified coordinates.
  - `get_block_neighbors(block)`: Retrieves the neighboring blocks for a given block.
  - `simulate()`: Executes one generation of the Game of Life by applying the rules to all blocks.
  - `animate()`: Continuously simulates and updates the board at a set interval.

### Simulation and Patterns

The project includes several predefined patterns that can be seeded on the board to observe their evolution:
- **Glider**: A small pattern that moves diagonally across the board.
- **Pulsar**: A large oscillating pattern.
- **Beacon**: A pattern that alternates between two states.
- **Toad**: A simple oscillator.
- **Diehard**: A pattern that takes many generations to stabilize.

The board can also be seeded randomly, and the simulation can be run step-by-step or animated continuously.

## How to Use

1. **Ensure Python 2.x is installed** on your system.
2. **Download or clone the project** and ensure `graphics.py` is in the same directory.
3. **Run the script** using Python 2:
   ```bash
   python game_of_life_template.py
3. **Experiment with Different Patterns**: modify the `if __name__ == '__main__':` section of the script. You can seed the board with different predefined patterns or customize the simulation settings to observe different behaviors. The provided patterns include Glider, Pulsar, Beacon, Toad, and Diehard, each demonstrating unique characteristics.

For example:
- **Glider**: A moving pattern that travels diagonally across the board.
- **Pulsar**: A large, oscillating pattern with a repeating cycle.
- **Beacon**: An alternating pattern that switches between two states.
- **Toad**: A simple pattern that oscillates between two configurations.
- **Diehard**: A pattern that takes many generations to stabilize.

You can also seed the board randomly and observe how different initial conditions lead to diverse outcomes. Experimenting with these patterns helps in understanding the intricate dynamics of Conway's Game of Life.

## Analysis

This implementation provides a visual and interactive platform to explore the dynamics of Conway's Game of Life. By experimenting with various initial configurations, users can observe how complex behaviors emerge from simple rules. The project illustrates key concepts in cellular automata, such as stability, oscillation, and chaos. It serves as a foundation for further exploration or customization of Conway's Game of Life, allowing users to delve deeper into the fascinating world of mathematical simulation and artificial life.

## Conclusion

Conway's Game of Life remains an intriguing topic in mathematics, computer science, and artificial life. This Python implementation offers an accessible means to visualize and experiment with this classic automaton, shedding light on the emergent behaviors that arise from simple interactions. The project not only serves as an educational tool but also as a platform for further exploration and experimentation with cellular automata.
