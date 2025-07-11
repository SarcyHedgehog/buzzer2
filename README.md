# Buzzer! A Real-Time Multiplayer Quiz App

Welcome to **Buzzer!**, a fast-paced, real-time multiplayer quiz game designed for mobile-first play. This app allows a host to run a true/false quiz for a group of friends, with live scoring and synchronized gameplay.

The entire application is built with modern, plain web technologies, showcasing the power of client-side state synchronization with **MultiSynq**.

## How to Play

1.  **Join/Create:** The first player creates a new game by choosing a simple, memorable **Game Code**. Other players join by entering the same code.
2.  **Become Host:** Any player can click the "Host" button to take control of the game.
3.  **Start the Game:** The Host waits for at least one other player to join and then clicks "Start Game."
4.  **Run the Quiz:**
    *   The Host asks a true/false question verbally.
    *   The Host selects the correct answer (✓ or ✗) on their screen. This opens the round for players.
    *   Players select their answer. Their first choice is locked in.
    *   The Host can see players' answers in real-time.
5.  **Next Question:** The Host clicks "Next Question." Scores are calculated, players are shown feedback on their last answer, and the host is immediately ready to set the answer for the next question.
6.  **End Game:** The Host can end the game at any time, which displays a final scoreboard to all players.

## How to Run Locally

This project is built to be run easily without any complex build tools.

#### 1. Prerequisites
*   A modern web browser (like Chrome or Firefox).
*   A simple local web server. The **Live Server** extension for VS Code is perfect for this.

#### 2. Clone the Repository
```bash
git clone https://github.com/SarcyHedgehog/buzzer2.git
cd buzzer2
```

#### 3. Configure MultiSynq Credentials (Crucial Step)

The game requires API credentials to connect to the MultiSynq backend. These are stored in a `config.js` file, which is **not** included in the repository for security.

*   **Copy the Example:** You'll find a `config.example.js` file. Copy this file and rename the copy to `config.js`.

*   **Edit `config.js`:** Open `config.js` and replace the placeholder values with your actual MultiSynq API Key and App ID.
    ```javascript
    // config.js
    window.APP_CONFIG = {
        API_KEY: "YOUR_MULTISYNQ_API_KEY_HERE", // Replace with your API Key
        APP_ID: "YOUR_MULTISYNQ_APP_ID_HERE"    // Replace with your App ID
    };
    ```
*   **Get Credentials:** You can get a free API Key from the [MultiSynq Coder Portal](https://multisynq.io/coder).

#### 4. Serve the Files
You **must** serve the files through a web server. You cannot just open `buzzer.html` directly from your file system.

*   **Using VS Code Live Server:** Right-click on `buzzer.html` in the explorer and choose "Open with Live Server".
*   This will open the app in your browser, and you're ready to play!

## How It Was Built

This project is a demonstration of a powerful, modern approach to building real-time web applications.

*   **Core Logic:** **[MultiSynq](https://multisynq.io/)** is used for all real-time state synchronization. The game follows a strict **Model-View** pattern, where the `GameModel` is the deterministic, synchronized source of truth, and the `GameView` is the UI that reacts to the model's state.
*   **Frontend:** The app is built with plain **HTML5** and modern **JavaScript (ES Modules)**, contained within a single `buzzer.html` file.
*   **Styling:** **[TailwindCSS](https://tailwindcss.com/)** is used for all styling, loaded via the Play CDN. This allows for rapid, utility-first styling without requiring a build step, making it ideal for self-contained projects.
*   **Progressive Web App (PWA):** The app includes a `manifest.json` and a minimal `sw.js` (service worker) to make it installable on mobile devices, allowing it to function like a native app when added to the home screen.