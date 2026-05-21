# ♟️ Code Strike Chess

**Code Strike Chess** is a fully functional, desktop-based chess engine built entirely from scratch in Java. This project was developed as a final thesis for a Data Structures and Algorithms (DSA) course. It features both Player vs. Player (PvP) and a challenging Player vs. Environment (PvE) Artificial Intelligence opponent.
<img width="1199" height="829" alt="image" src="https://github.com/user-attachments/assets/5401651c-9b80-4d9a-81b3-778cc4d5a610" />


## ✨ Features
* **Full FIDE Rule Compliance:** Supports complex mechanics including Castling, En Passant, and Pawn Promotion.
* **Playable AI Bot:** Play against a smart computer opponent powered by advanced search algorithms.
* **Draw Detection:** Automatically detects draws via the 50-Move Rule, Insufficient Material, and 3-Fold Repetition.
* **Custom UI & Audio:** Smooth 60 FPS rendering using Java Swing/AWT, featuring move highlighting, captured piece tracking, and dynamic sound effects.

## 🧠 Data Structures & Algorithms (Under the Hood)
Because this is a DSA project, the engine avoids external game libraries and is built on raw, optimized data structures:

* **Object-Oriented Architecture:** Uses heavily applied Abstraction and Polymorphism. An abstract `piece` base class allows subclasses (like `Knight` or `Pawn`) to manage their own unique movement logic.
* **O(1) Data Lookups (2D Arrays):** The board is mapped to a `piece[8][8]` matrix, allowing for instant, constant-time coordinate validation.
* **Dynamic Memory (ArrayLists):** Active pieces are tracked dynamically, preventing null-pointer gaps and ensuring fast O(N) iteration for the graphics rendering loop.
* **State Serialization (HashMaps):** To enforce the 3-Fold Repetition rule without lagging the game, board states are converted to String IDs and stored in a HashMap, granting near O(1) lookup times.
* **Recursive AI (Minimax & Game Trees):** The AI evaluates thousands of future board states by recursively traversing a Game Tree.
* **Optimization (Alpha-Beta Pruning & Sorting):** To prevent the AI from freezing the game due to exponential $O(b^d)$ growth, the engine uses custom sorting comparators to evaluate the best moves (captures/promotions) first. This allows Alpha-Beta pruning to cut off useless branches efficiently.

## 📂 Project Structure
* `main/` - Contains the application entry point, 60 FPS game loop (`GamePanel`), and UI/Input listeners.
* `piece/` - Contains the abstract base class and all individual chess piece logic.
* `computer/` - Houses the `BotChess` AI engine, evaluation matrices, and move generation logic.

## 🚀 How to Run

### Prerequisites
* Java Development Kit (JDK) 8 or higher installed on your machine.

### Installation & Execution
1. Clone the repository:
   ```bash
   git clone [https://github.com/yourusername/code-strike-chess.git](https://github.com/yourusername/code-strike-chess.git)
2. Open the project in your preferred IDE (Visual Studio Code, IntelliJ, Eclipse).

3. Locate the main entry file (src/main/main.java or similar).

4. Compile and Run the project.
