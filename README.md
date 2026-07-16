# Phishing Detective

Phishing Detective is an interactive URL-identification game for Lesson 2. Each round presents 10 randomly selected URLs and explains the answer immediately after every choice.

> The assignment specifies the filename `phising_url.json` with one "h" missing. This project keeps that spelling to match the original instructions.

## Files

- `index.html` contains the complete interface, styling, and game logic. It has no external dependencies.
- `phising_url.json` contains 50 safe teaching examples: 25 legitimate URLs and 25 phishing-style URLs.

## How to Play

### Option 1: Open the file directly

1. Make sure the computer can access GitHub.
2. Double-click `index.html`. The browser will load the question bank from this repository's GitHub Raw URL.
3. Select **Legitimate website** or **Phishing trap** for each question.

### Option 2: Run a local server (recommended)

Open PowerShell in this folder and run:

```powershell
python -m http.server 8000
```

Open <http://localhost:8000> in a browser. Press `Ctrl+C` in PowerShell when finished.

If Python is unavailable, open `index.html` with the **Live Server** extension in VS Code.

### Option 3: Use the online GitHub Pages version

Visit <https://smallcarrotqwq.github.io/fishing_game/>.

The deployment source is configured in **Settings → Pages** as the `main` branch and `/ (root)` folder.

## Editing the Question Bank

Edit `phising_url.json`. Every question must follow this format:

```json
{
  "url": "https://example.com",
  "isPhishing": false,
  "explanation": "Explain the reason for the answer here."
}
```

- `isPhishing: true` marks a phishing-style URL.
- `isPhishing: false` marks a legitimate URL.
- The question bank must contain at least 10 entries.
- Never add active malicious URLs. Use reserved `.test`, `.invalid`, `example.com/.net/.org`, or documentation-only IP addresses for teaching examples.

After changes are pushed, both GitHub Pages and the directly opened version will load the latest question bank.
