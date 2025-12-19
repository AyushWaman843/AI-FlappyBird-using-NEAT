Flappy Bird with AI
A Python implementation of Flappy Bird featuring both manual gameplay and AI learning using the NEAT (NeuroEvolution of Augmenting Topologies) algorithm.

Overview
This project includes two versions of the classic Flappy Bird game:

Manual Play (falppybird.py): Play the game yourself using the spacebar
AI Training (flappybirdai.py): Watch AI agents learn to play using neural networks and genetic algorithms
Features
Classic Flappy Bird gameplay mechanics
Smooth animations with multiple bird sprites
Collision detection using pixel-perfect masks
Score tracking
AI learning through NEAT algorithm with generation counter
Configurable neural network parameters
Requirements
pygame
neat-python
Install dependencies:

bash
pip install pygame neat-python
```

## Project Structure
```
├── flappybirdai.py          # AI version with NEAT algorithm
├── falppybird.py            # Manual play version
├── config-feedforward.txt   # NEAT configuration file
└── imgs/                    # Image assets folder
    ├── bird1.png
    ├── bird2.png
    ├── bird3.png
    ├── pipe.png
    ├── base.png
    └── bg.png
How to Play
Manual Version
bash
python falppybird.py
Press SPACE to make the bird jump
Avoid pipes and the ground
Try to get the highest score!
AI Training Version
bash
python flappybirdai.py
Watch as AI agents learn to play over multiple generations
The generation number and score are displayed on screen
AI uses 3 inputs: bird's y-position, distance to pipe height, distance to pipe bottom
Training runs for 50 generations with a population of 30 birds per generation
NEAT Configuration
The AI version uses a feedforward neural network configured in config-feedforward.txt:

Population size: 30 birds per generation
Inputs: 3 (bird position, pipe distances)
Outputs: 1 (jump or don't jump)
Activation function: tanh
Fitness threshold: 100
Max generations: 50
Game Mechanics
Bird Physics: Gravity simulation with upward velocity on jump
Pipe Gap: 200 pixels between top and bottom pipes
Scroll Speed: 6 pixels per frame
Score: +1 for each pipe successfully passed
AI Fitness: +0.1 per frame survived, +5 per pipe passed, -1 for collision
Customization
You can modify game parameters in the code:

Window size: win_width and win_height
Pipe gap: Pipe.gap
Game speed: clock.tick(30)
NEAT parameters: Edit config-feedforward.txt
How the AI Works
The NEAT algorithm evolves neural networks over generations:

Each generation starts with 30 birds with random neural networks
Birds receive fitness based on survival time and pipes passed
Better-performing birds are selected for reproduction
Networks mutate and crossover to create the next generation
Over time, birds learn optimal jumping patterns

Credits
Built with Pygame and NEAT-Python. Classic Flappy Bird gameplay mechanics recreated for educational purposes.

