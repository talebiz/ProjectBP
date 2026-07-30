# Gliński's Hexagonal Chess ♞⬡

A fully functional implementation of **Gliński's Hexagonal Chess** in Java. This project was developed as a final assignment for a Fundamentals of Programming course, emphasizing Object-Oriented Programming (OOP) principles, algorithmic logic, and manual state management.

---

## 📌 Overview

This project adapts traditional chess rules to a 91-cell hexagonal board. The game features a graphical user interface (GUI) and strictly enforces Gliński's specific coordinate system and complex piece movement rules. 

### Core Features
* **Hexagonal Coordinate System:** Custom grid mapping (columns `a` to `l`, skipping `j`, and rows `1` to `11` bending at 60-degree angles).
* **Valid Movement Logic:** Strict enforcement of piece movements, captures, and boundaries tailored to the hexagonal geometry.
* **Game States:** Real-time calculation of Check, Checkmate, and Stalemate conditions.
* **Pawn Promotion:** Interactive popup allowing players to promote pawns to a Queen, Rook, Bishop, or Knight.
* **Custom Save/Load System:** A fully manual file I/O mechanism to save and resume game states without relying on external libraries (JSON and Java Serialization are strictly prohibited).
* **GUI Integration:** Seamless connection between the backend game logic and the provided Swing-based graphical interface.

---

## 🏗️ Architecture & Design

The project is heavily decoupled, separating the core chess logic from the graphical rendering to adhere to OOP best practices.

* **`Application` (GUI Manager):** Provided by the course, this class handles the rendering of the board, pieces (via Unicode), popups, and turn messages.
* **`EventListener` Interface:** The crucial bridge between user GUI actions and backend game logic. It implements:
  * `onClick(int row, char col)`: Processes piece selection, calculates valid moves, updates cell background colors (e.g., highlighting valid paths in blue), and executes movements.
  * `onSave(File file)`: Serializes the current board state, captured pieces, and turn information into a custom string format.
  * `onLoad(File file)`: Parses the custom text file to perfectly reconstruct the board state.
  * `onNewGame()`: Clears the board and resets pieces to the default Gliński's setup.

---

## 🚀 Getting Started

### Prerequisites
* **Java Development Kit (JDK):** Version 8 or higher is recommended.
* **IDE/Compiler:** IntelliJ IDEA, Eclipse, or standard command-line Java tools.
* **OS:** A desktop environment is required to render the Java Swing GUI (cannot be run in a headless or web-based IDE).

### Installation & Execution
1. Clone or download the repository.
2. Open the project in your preferred Java IDE.
3. Ensure the provided graphics package (`ir.sharif.math.bp02_1.hex_chess`) is properly linked.
4. Locate and run the `Main.java` file (located in the root package).

---

## 🕹️ How to Play

1. **Starting the Game:** Upon running the application, the board will automatically initialize with the standard setup and announce "White's Turn" at the bottom of the screen.
2. **Moving Pieces:** Click on a piece to select it (the background will highlight). Click on a valid destination cell to move. Attempting an invalid move will be blocked by the game logic.
3. **Capturing:** Capturing works by landing on an opponent's piece. Captured pieces will instantly appear in the "removed pieces" panel on the right side of the screen.
4. **Saving/Loading:** Use the "File" menu in the top-left corner to save your current progress or load a previously saved game file to resume playing later.

---

## ⚙️ Development Constraints & Notes
* **No External Libraries:** The core logic, including the save/load system, is built entirely using standard Java utilities.
* **Manual Serialization:** The save files dictate piece positions, colors, and the current turn using a proprietary string-based structure designed specifically for this project's requirements.

---
*Designed to demonstrate proficiency in OOP, algorithmic thinking, and custom file manipulation.*
