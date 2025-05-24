# QuizWhiz

## Overview
QuizWhiz is an interactive Python-based quiz application for engaging knowledge testing across categories and difficulty levels. It offers single-player, multiplayer, and learning modes, with adaptive difficulty, a shop for hints/lives, performance analytics, and a SQLite leaderboard. QuizMaster manages the JSON question database, allowing view/add/edit/delete operations with `difflib` similarity checks to ensure uniqueness. Both are modular, extensible, and user-friendly, with optional `rich` console formatting and `playsound` audio feedback.

## Features

### QuizWhiz
- **Multiple Modes**:
  - Single-Player Quiz: Customizable question sets with adaptive difficulty.
  - Multiplayer: Players compete on shared questions.
  - Learning Mode: Review questions/answers without scoring.
- **Question Types**:
  - True/False (text-based).
  - Multiple-choice (single answer).
  - Multiple-select (multiple answers).
  - Coding (Python/JavaScript, placeholder evaluation).
- **Adaptive Difficulty**: Adjusts based on performance (e.g., harder after three correct).
- **Shop System**: Buy hints (10 coins) or lives (20 coins).
- **Progress Tracking**: Saves profiles (scores, coins, progress) in `profiles.json`.
- **Leaderboard**: Top 5 scores in `leaderboard.db` (SQLite).
- **Timed Inputs**: Threading-based timers (30s easy, 45s medium, 60s hard).
- **Achievements**: Rewards for milestones (e.g., perfect score).
- **Analytics**: Category-wise stats, weak area detection.
- **Clipboard Support**: Copy results (requires `pyperclip`).
- **Audio Feedback**: Sounds for answers (requires `playsound`, `correct.wav`, `incorrect.wav`).
- **Rich Console UI**: Formatted output (requires `rich`).

### QuizMaster
- **Question Management**: View/add/edit/delete questions in `questions.json`.
- **Similarity Check**: `difflib` detects 80% similar questions.
- **ID Management**: Auto-assigns unique IDs.
- **Flexible Editing**: Update specific fields, preserve others.

## Installation

### Prerequisites
- Python 3.6+.
- Optional libraries:
  ```
  pip install rich
  ```
  ```
  pip install playsound
  ```
  ```
  pip install pyperclip
  ```
- Audio files (`correct.wav`, `incorrect.wav`) in project directory.

### Setup
1. Clone repository:
  ```
  git clone <repository-url>
  cd quiz_project
  ```
2. Ensure `questions.json` exists (sample provided, 222 questions).
3. Install optional dependencies:
  ```
  pip install rich playsound pyperclip
  ```
4. Place `correct.wav`, `incorrect.wav` in project directory (optional).

## Usage

### Running QuizWhiz
1. Execute:
  ```
  python quiz_whiz.py
  ```
2. Enter username (skip for learning mode).
3. Choose mode:
   - Quiz: Select category, difficulty, question count (1–50).
   - Learning: Review questions/answers.
   - Multiplayer: Enter player usernames, compete.
   - Leaderboard: View top 5 scores.
   - Shop: Buy hints/lives.
   - Exit: Save and quit.
4. Follow prompts for questions, shop, or analytics.

### Running QuizMaster
1. Execute:
  ```
  python quizmaster.py
  ```
2. Choose:
   - View Questions: List all in `questions.json`.
   - Add Question: Input type, text, answer, metadata.
   - Edit Question: Modify by ID.
   - Delete Question: Remove by ID.
   - Save and Exit: Save changes.
3. Follow prompts to manage questions.

## File Structure
- `quiz_whiz.py`: Main quiz app.
- `quizmaster.py`: Question management tool.
- `questions.json`: Question database.
- `profiles.json`: User profiles (auto-generated).
- `leaderboard.db`: SQLite leaderboard (auto-generated).
- `correct.wav`, `incorrect.wav`: Optional audio.
- `README.md`: Documentation.

## Sample Question Format (`questions.json`)
```
{
    "text": "The Python code `print(2 ** 3)` outputs 8",
    "answer": true,
    "explanation": "Python’s `**` computes 2³, outputting 8.",
    "difficulty": "easy",
    "category": "Coding",
    "type": "code",
    "language": "python",
    "id": 70
}
```

## Dependencies
- **Standard**: `json`, `random`, `sqlite3`, `os`, `time`, `threading`, `difflib`.
- **Optional**:
  - `rich`: Console formatting.
  - `playsound`: Audio.
  - `pyperclip`: Clipboard.
- Fallback to plain-text or skips audio/clipboard if missing.

## Notes
- `questions.json` required for QuizWhiz.
- `leaderboard.db`, `profiles.json` auto-generated.
- Coding questions use placeholder `exec`; enhance with test cases for production.
- Similarity checks use 80% threshold.
- Audio files optional, user-provided.

## Potential Improvements
- GUI with `tkinter` or `PyQt`.
- Web version with Flask/Django.
- Automated test cases for coding questions.
- Image-based questions or multimedia hints.
- Paginated SQLite queries for large leaderboards.

## Contributing
1. Fork repository.
2. Create branch:
  ```
  git checkout -b feature-name
  ```
3. Commit:
  ```
  git commit -m "Add feature"
  ```
4. Push:
  ```
  git push origin feature-name
  ```
5. Submit pull request.

## License
MIT License. See [LICENSE](LICENSE).

## Contact
Open an issue or email [shreyas.venur@gmail.com] for feedback.
