# Programming Time Tracker

A powerful VS Code extension for tracking your programming time, maintaining coding streaks, and staying motivated with a gamified points system.

![VS Code](https://img.shields.io/badge/VS%20Code-1.74.0+-007ACC?style=flat&logo=visual-studio-code)
![TypeScript](https://img.shields.io/badge/TypeScript-4.9.3-3178C6?style=flat&logo=typescript)
![License](https://img.shields.io/badge/License-MIT-green)

## 📋 Table of Contents

- [Features](#features)
- [Technology Stack](#technology-stack)
- [Installation](#installation)
- [How to Use](#how-to-use)
- [Commands](#commands)
- [Data Storage](#data-storage)
- [Contributing](#contributing)
- [License](#license)

## ✨ Features

### ⏱️ Time Tracking
- Start and stop a timer to track your programming sessions
- Real-time display of elapsed time in the status bar
- Multiple sessions support per day
- Automatic calculation of total daily programming time

### 🎯 Points System
- Earn **100 points per hour** of coding
- Points are accumulated and displayed in the status bar
- Use points in the built-in mini-game (slot machine)

### 🔥 Coding Streaks
- Track your current coding streak
- View your longest streak ever
- 7-day contribution graph showing your coding activity
- Visual dashboard with detailed statistics

### 📊 Dashboard
- Interactive webview dashboard
- Current streak and longest streak display
- Daily coding time breakdown
- Contribution heatmap for the last 7 days

## 🛠️ Technology Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| **TypeScript** | ^4.9.3 | Primary programming language |
| **VS Code API** | ^1.74.0 | Extension framework |
| **Node.js** | 16.x | Runtime environment |
| **ESLint** | ^8.28.0 | Code linting |
| **@typescript-eslint** | ^5.45.0 | TypeScript linting support |
| **VSCE** | Latest | Extension packaging tool |

### Architecture
- **Frontend**: HTML/CSS/JavaScript (embedded webview)
- **Backend**: TypeScript using VS Code Extension API
- **Data Persistence**: VS Code globalState API
- **Build System**: TypeScript Compiler (tsc)

## 📦 Installation

### From Source

1. Clone the repository:
```bash
git clone <repository-url>
cd programming-time-tracker
```

2. Install dependencies:
```bash
npm install
```

3. Compile TypeScript:
```bash
npm run compile
# or for watch mode
npm run watch
```

4. Open in VS Code:
```bash
code .
```

5. Press `F5` to launch the extension in development mode

### Package as .vsix

To create a distributable .vsix file:
```bash
npm run package
```

The package will be generated in the project root directory.

## 🎮 How to Use

### Getting Started

1. **Launch the Extension**: Press `F5` in VS Code (development mode) or install the .vsix package

2. **Open Command Palette**: Press `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (macOS)

3. **Start Tracking**: Run the "Start Programming Timer" command

### Basic Workflow

1. **Start Timer**: Click the status bar button or use the command palette
2. **Code**: Work on your projects as usual
3. **Stop Timer**: Click the stop button or use the command when done
4. **View Stats**: Open the streak dashboard to see your progress

### Status Bar Items

The extension adds three items to your status bar:
- **Timer Display**: Shows current/elapsed programming time
- **Start/Stop Button**: Toggle timer on/off
- **Points Display**: Shows your total points

## 📝 Commands

| Command | Description |
|---------|-------------|
| `Start Programming Timer` | Starts the coding timer |
| `Stop Programming Timer` | Stops the timer and saves the session |
| `Toggle Programming Timer` | Toggles timer on/off |
| `Show Programming Time` | Displays current total time |
| `Show Coding Streak Dashboard` | Opens the streak dashboard |

### Accessing Commands

1. **Command Palette**: `Ctrl+Shift+P` → Type command name
2. **Status Bar**: Click the timer/points items
3. **Keyboard Shortcuts**: Assign custom shortcuts in VS Code settings

## 💾 Data Storage

All data is stored locally using VS Code's globalState API:
- **Coding Sessions**: Date, start time, end time, duration
- **Points**: Total accumulated points
- **Streaks**: Daily coding data for streak calculation

Data persists across VS Code sessions and restarts.

### Data Structure
```typescript
interface DailyCodingData {
    date: string;           // ISO date string (YYYY-MM-DD)
    totalTime: number;     // Total milliseconds
    sessions: {
        start: Date;
        end: Date;
        duration: number;
    }[];
}
```

## 🎰 Points & Gamification

### Earning Points
- **100 points per hour** of tracked programming time
- Points are awarded when you stop the timer
- Minimum 1 point for any session

### Using Points
- Open the Streak Dashboard
- Use the slot machine game to gamble your points
- Win multipliers or lose points (game of chance!)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and test thoroughly
4. Run linting: `npm run lint`
5. Commit your changes: `git commit -m 'Add feature'`
6. Push to the branch: `git push origin feature-name`
7. Submit a pull request

### Development Commands

```bash
# Build the extension
npm run build

# Watch for changes
npm run watch

# Run tests
npm test

# Lint code
npm run lint

# Package extension
npm run package
```


## 🙏 Acknowledgments

- VS Code Extension API documentation
- TypeScript handbook
- ESLint configuration guides

---