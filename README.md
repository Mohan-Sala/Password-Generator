
# 🔐 SecurePass — Modern Password Generator

> A portfolio-grade, futuristic password generator web app built with vanilla HTML, CSS, and JavaScript. Zero dependencies, zero backend — runs entirely in the browser.

---

## ✨ Features

### Core
- **Password Display** — Real-time generation with color-coded character types
- **Length Slider** — Adjustable from 4 to 32 characters with auto-generate
- **Character Toggles** — Uppercase, lowercase, numbers, symbols
- **One-Click Copy** — Copy to clipboard with animated toast notification
- **Regenerate** — Instant reshuffle with rotation animation

### Advanced
- **Strength Meter** — Visual bar with Weak / Medium / Strong / Very Strong ratings
- **Entropy Score** — Cryptographic entropy calculated in real-time (bits)
- **Crack Time Estimation** — Shows how long a high-end GPU would take to brute-force
- **Password History** — Last 5 passwords stored in `localStorage`, click-to-reuse
- **Dark / Light Mode** — System-aware theme toggle with smooth transitions
- **Export to TXT** — Download generated password as a `.txt` file
- **Security Tips Panel** — 4 actionable best-practice tips for users

### Bonus
- **Exclude Similar Characters** — Removes `O`, `0`, `l`, `1`, `I` to avoid confusion
- **No Duplicate Characters** — Ensures every character is unique (respects pool limits)
- **Auto-Generate on Change** — Updates password instantly when any setting changes
- **Keyboard Shortcuts** — `Ctrl/Cmd + G` to generate, `Ctrl/Cmd + C` to copy

---

### Design System
- **Theme:** Dark + Neon Tech UI
- **Accent Colors:** Indigo `#6366F1` · Purple `#A855F7` · Pink `#EC4899`
- **Card Background:** `#11163A` (glassmorphism with backdrop blur)
- **Typography:** Inter (body) · JetBrains Mono (password display)
- **Effects:** Animated starfield, gradient orbs, shimmer strength bar

---

## 🚀 Quick Start

### Option 1: Open Directly
Simply open `password_generator.html` in any modern browser. No server required.

```bash
# Clone the repo
git clone https://github.com/yourusername/securepass.git
cd securepass

# Open in browser (macOS)
open password_generator.html

# Open in browser (Linux)
xdg-open password_generator.html
```

### Option 2: Serve Locally
```bash
# Python 3
python -m http.server 8080

# Node.js (npx)
npx serve .

# Then visit http://localhost:8080
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **HTML5** | Semantic structure |
| **CSS3** | Custom animations, glassmorphism, responsive grid |
| **Tailwind CSS (CDN)** | Utility-first styling |
| **Vanilla JavaScript** | All logic — generation, entropy, UI state |
| **Web Crypto API** | Cryptographically secure random values |
| **localStorage** | Persistent password history |

> **Zero build step. Zero npm install. Zero backend.**

---

## 📁 Project Structure

```
securepass/
├── password_generator.html    # Single-file complete application
├── README.md                  # This file
├── LICENSE                    # MIT License
└── assets/
    └── screenshot.png         # (Optional) Add your own screenshots
```

---

## 🧠 How It Works

### Password Generation
1. Builds a character pool based on selected toggles
2. Optionally filters out visually similar characters
3. Ensures at least one character from each selected type
4. Fills remaining length with cryptographically random picks
5. Shuffles the result using Fisher-Yates via `crypto.getRandomValues()`

### Entropy Calculation
```
Entropy (bits) = password_length × log₂(pool_size)
```

### Crack Time Estimation
Assumes a high-end GPU cluster capable of **10 billion guesses/second**:
```
time = (pool_size ^ length) / (guesses_per_sec × 2)
```

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl / Cmd + G` | Generate new password |
| `Ctrl / Cmd + C` | Copy current password to clipboard |

---

## 🎨 Customization

### Changing Colors
Edit the Tailwind config inside the `<script>` tag:
```javascript
tailwind.config = {
    theme: {
        extend: {
            colors: {
                primary: '#6366F1',   // Change this
                secondary: '#A855F7', // Change this
            }
        }
    }
}
```

### Changing Default Length
```javascript
let state = {
    length: 16,  // Change default here
    // ...
}
```

### Changing History Limit
```javascript
if (state.history.length > 5) state.history.pop();  // Change 5 to your limit
```

---

## 🌐 Browser Support

| Browser | Support |
|---------|---------|
| Chrome 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Edge 90+ | ✅ Full |
| Opera 76+ | ✅ Full |

> Requires `crypto.getRandomValues()` and `Clipboard API` support.



---

## 🤝 Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- [Tailwind CSS](https://tailwindcss.com/) for the utility-first CSS framework
- [Inter](https://rsms.me/inter/) & [JetBrains Mono](https://www.jetbrains.com/lp/mono/) fonts
- Inspired by modern SaaS dashboards and cybersecurity tools

---

