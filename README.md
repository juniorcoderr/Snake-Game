# 🐍 Snake Game using Python Turtle Graphics

Welcome to the **classic Snake Game** recreated in Python using the built-in `turtle` module. This project is a modular, object-oriented implementation of the traditional Snake game with collision detection, score tracking, dynamic food spawning, and responsive keyboard controls.

> 🍽️ Eat the food.  
> 🐍 Grow longer.  
> 💥 Avoid hitting walls or yourself.  
> 📈 Beat your high score!

---

## 🧠 Core Concepts and Technologies Used

### ✅ **Python Turtle Graphics**
- The `turtle` module provides a simple way to create animations and visuals.
- Perfect for beginners to understand coordinate systems, object movement, and event-driven programming.

### ✅ **Object-Oriented Programming (OOP)**
- The code is structured into separate classes (`Snake`, `Food`, `Scoreboard`) to promote modularity and reusability.
- Encapsulation of responsibilities ensures clean and maintainable code.

### ✅ **Event Handling**
- Real-time keyboard inputs are handled using `screen.onkey()` to control the snake’s movement direction.

### ✅ **Game Loop**
- A continuous `while` loop runs the game, updating the screen and checking for interactions like:
  - Eating food
  - Collisions with walls
  - Collisions with tail

---

## 📁 File Structure & Responsibilities

```plaintext
snake-game/
│
├── main.py            # Main entry point, initializes and runs the game loop
├── snake.py           # Snake class: controls movement, growth, direction logic
├── food.py            # Food class: creates and randomly places food on the screen
└── scoreboard.py      # Scoreboard class: tracks and displays score, handles game over message
```

---

## 🔍 Detailed Breakdown

### `main.py`
- Initializes the game screen (600x600 pixels, black background).
- Creates instances of the main components: `Snake`, `Food`, and `Scoreboard`.
- Sets up keyboard bindings for movement.
- Contains the main game loop:
  - Moves the snake at fixed intervals (`time.sleep(0.1)`).
  - Detects:
    - **Food Collision**: If distance between snake’s head and food is `< 15`, extend the snake and increase the score.
    - **Wall Collision**: If the snake’s head crosses the screen boundary, end the game.
    - **Tail Collision**: If the snake's head collides with any body segment, end the game.

---

### `snake.py` — 🐍 Snake Logic
Handles:
- Initial snake creation with 3 segments at fixed positions.
- Continuous movement by shifting each segment to the position of the previous one.
- Growing the snake by adding segments at the tail.
- Validating turns to prevent 180° reverse movement (e.g., can't go from `Up` to `Down` directly).
  
Key Methods:
- `move()`: Moves each segment in reverse order.
- `extend()`: Adds a new segment at the end.
- Direction methods (`up()`, `down()`, `left()`, `right()`): Change heading with safety checks.

---

### `food.py` — 🍏 Food Mechanics
- Inherits from `Turtle`.
- Displays a small blue circle (scaled to 0.5) representing the food.
- Uses `random.randint` to generate new x and y coordinates within the playable area.
- `refresh()` method repositions food after each collision with the snake.

---

### `scoreboard.py` — 📊 Score Tracking
- Inherits from `Turtle` to display text on the screen.
- Initializes with a score of 0 and positions the score at the top center.
- On eating food:
  - Score increases
  - Screen is cleared and updated
- On game over:
  - Displays “GAME OVER” text at the center.

Key Methods:
- `increase_score()`: Increments and updates the score.
- `game_over()`: Ends the game and displays the message.

---

## 🎮 Controls

| Key      | Function     |
|----------|--------------|
| `⬆️ Up`    | Move Snake Up    |
| `⬇️ Down`  | Move Snake Down  |
| `⬅️ Left`  | Move Snake Left  |
| `➡️ Right` | Move Snake Right |

> ⚠️ Reverse directions are disabled to prevent instant self-collision!

---

## 🖥️ How to Run the Game

1. Ensure Python 3.x is installed.
2. Clone this repository:
   ```bash
   git clone https://github.com/juniorcoderr/Snake-Game.git
   cd snake-game-python
   ```
3. Run the game:
   ```bash
   python main.py
   ```

✅ No external libraries required!

---

## 🚀 Potential Enhancements

Here are some ideas for upgrading the game further:
- 🏆 High score saving (using a file or database)
- 🔊 Add sound effects (e.g., using `pygame`)
- 🐢 Add snake speed levels or difficulty modes
- 🎨 Custom themes/skins
- 📱 Mobile-compatible version (e.g., using Kivy)
- 🌐 Web version using JavaScript or Pygame Zero

---

## 🙌 Credits

Developed by [Vinayak Yadav](https://github.com/juniorcoderr)  
Inspired by classic Snake arcade games and Python beginner projects.
