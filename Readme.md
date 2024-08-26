# Sahil's Turn-Based Chess-Like Game with WebSocket Communication

## Overview

I have tried creating a turn-based chess-like game designed for real-time play using WebSocket communication. Players control teams of characters on a 5x5 grid, aiming to capture their opponent’s pieces. The game features unique movement rules for each character and interactive gameplay through a web-based interface.

## Components

### 1. Server
- **Language**: Node.js
- **Responsibilities**:
  - **Game Logic**: Implement core game rules and mechanics.
  - **WebSocket Server**: Set up and manage WebSocket communication.
  - **Game State**: Maintain and update the game state.
  - **Broadcasting**: Send game state updates and notifications to clients.

### 2. WebSocket Layer
- **Responsibilities**:
  - **Real-Time Communication**: Facilitate real-time interaction between server and clients.
  - **Event Handling**: Manage events for game initialization, moves, state updates, and notifications.

### 3. Web Client
- **Technologies**: HTML, CSS, JavaScript
- **Responsibilities**:
  - **UI Rendering**: Display the game board and character controls.
  - **WebSocket Communication**: Send and receive data from the server.
  - **Game Interaction**: Handle player input and update the game display based on server responses.

## Game Rules

### Setup
- **Grid Size**: 5x5
- **Characters per Player**: 5 (Pawns, Hero1, Hero2)
- **Initial Setup**: Each player arranges their characters on their respective starting rows.

### Characters and Movement

#### Pawn
- **Movement**: Moves one block in any direction (Left, Right, Forward, Backward).

#### Hero1
- **Movement**: Moves two blocks straight in any direction.
- **Combat**: Captures any opponent’s character in its path.

#### Hero2
- **Movement**: Moves two blocks diagonally in any direction.
- **Combat**: Captures any opponent’s character in its path.
- **Move Commands**: FL (Forward Left), FR (Forward Right), BL (Backward Left), BR (Backward Right)

### Game Flow

- **Turns**: Players alternate turns, making one move per turn.
- **Combat**: Characters capture opponent’s pieces if they move into the same position.
- **Invalid Moves**: Moves are considered invalid if:
  - They go out of bounds.
  - They do not match the character's movement rules.
  - They target a friendly piece.
- **Game State Display**: Shows the current configuration of the 5x5 grid and the positions of all characters.
- **Winning**: The game ends when one player eliminates all of the opponent’s characters.

### Features

- **Move History**: Displays a log of all moves made during the game.
- **Error Handling**: Alerts players to invalid moves or other issues.
- **Real-Time Updates**: Ensures all players have the most current game state through WebSocket communication.

## Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/your-repo.git
   cd your-repo
   ```

2. **Install Dependencies**
   - For the server:
     ```bash
     npm install
     ```
   - For the client, dependencies are included in the HTML and will be served with the static files.

3. **Run the Server**
   ```bash
   node server.js
   ```

4. **Open the Game**
   - Open `index.html` in your web browser to start playing.