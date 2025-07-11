# 🟢 Buzzer

A simple Progressive Web App (PWA) multiplayer buzzer  powered by [Multisynq](https://multisynq.io), designed for AI-assisted Vibe Coding experiments.

## 🚀 Overview

This game allows players to join a lobby via a 5-letter room code and interact using a green ✅ or red ❌ buzzer. It supports session hosting, live player counts, scores, and a host-controlled round system.

## 🎮 Features

- Multiplayer buzzer game with instant feedback
- Host-led round start/stop and scoreboard
- Scoring logic with win/loss buttons
- ReactTogether/Multisynq backend (no servers!)
- Works as a PWA (can be installed on desktop/mobile)
- Responsive UI using Tailwind CSS

## 🧪 Local Development

### 1. Clone the repository

```bash
git clone https://github.com/SarcyHedgehog/buzzer2.git
cd buzzer2
```

### 2. Create your local `config.js`

> This file must not be committed — it should remain local and listed in `.gitignore`.

```js
// config.js - DO NOT COMMIT THIS FILE!
window.APP_CONFIG = {
  API_KEY: "your-local-api-key",
  APP_ID: "com.sarcastichedgehog.buzzer",
  BASE_URL: "http://localhost:8000"
};
```

### 3. Start a local server

```bash
python -m http.server
```

Visit `http://localhost:8000`.

---

## 🔧 Deployment to Website (GitHub Actions)

### Required GitHub Secrets

Ensure your repo contains the following secrets:

- `MULTISYNQ_API_KEY`
- `MULTISYNQ_APP_ID`
- `MULTISYNQ_BASE_URL` (e.g., `https://www.sarcastichedgehog.com/buzzer`)

### Deployment YAML snippet

```yaml
- name: Create config.js for buzzer
  working-directory: ./buzzer_game
  run: |
    echo "Generating config.js from secrets..."
    echo "window.APP_CONFIG = {" > config.js
    echo "  API_KEY: \"${{ secrets.MULTISYNQ_API_KEY }}\"," >> config.js
    echo "  APP_ID: \"${{ secrets.MULTISYNQ_APP_ID }}\"," >> config.js
    echo "  BASE_URL: \"${{ secrets.MULTISYNQ_BASE_URL }}\"" >> config.js
    echo "};" >> config.js
```

This generates `config.js` dynamically at deploy time, keeping secrets safe.

> ⚠️ Always regenerate `config.js` on deployment — do **not** skip it based on file existence.

---

## 📲 Progressive Web App

This app is installable as a PWA:

- Add to Home Screen (Android/iOS)
- Installable as a standalone app on desktop
- Supports offline caching and startup banners

No additional configuration needed beyond `manifest.json` and `sw.js`.

---

## 🧠 Powered By

- [Multisynq](https://multisynq.io)
- Vanilla JS / HTML / Tailwind CSS
- GitHub Actions for deployment
- <a href="https://www.sarcastichedgehog.com" target="_blank">
    <img src="https://www.sarcastichedgehog.com/images/hedgehog_logo.png" alt="Sarcastic Hedgehog" width="20" height="20" style="vertical-align: middle;"/> Sarcastic Hedgehog
  </a>
---

## 📸 Screenshot

![Screenshot](https://www.sarcastichedgehog.com/images/buzzer.png)

---

## 🧩 License

MIT