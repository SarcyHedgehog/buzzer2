# Buzzer: Multiplayer True/False Game

A minimal multiplayer quiz-style game built with [Multisynq](https://multisynq.io) and Vibe Coding principles. Players join a shared room to answer true/false questions in real time, with scores tracked and displayed.

## 🚀 Features

- Join or host a multiplayer room
- Synced player presence
- True/False button interface
- Scoreboard and host controls
- Built using [Multisynq](https://multisynq.io), a decentralized, serverless multiplayer framework
- No server needed — fully browser-native

## 🧠 Controls & Gameplay

- Use the green ✅ and red ❌ buttons to answer each question
- The host controls when questions start and end
- Points are awarded for correct answers; the scoreboard updates live

## 📦 Files

- `index.html` — main UI and game logic
- `config.js` — runtime configuration (API key & App ID)
- `config.example.js` — template for creating your own `config.js`
- `sw.js` — service worker (for PWA support)
- `manifest.json` — PWA metadata

## 📲 Progressive Web App (PWA)

This app is PWA-enabled, which means:

- You can install it on your device (desktop or mobile)
- It supports offline startup via the cached `index.html`
- Includes a `manifest.json` and basic `sw.js` for service worker behavior

To install:

1. Open the app in Chrome or Edge
2. Click the install icon in the address bar
3. Launch from your home screen or app list

## 🔐 Configuration

Before running the app, create a `config.js` file with the following content:

```js
window.APP_CONFIG = {
  API_KEY: "your-multisynq-api-key",
  APP_ID: "com.yourdomain.buzzer"
};
```

See `config.example.js` for a sample.

## 🛰 Deployment

This app is designed to run from any static web host (GitHub Pages, Netlify, etc). No build step required.

A GitHub Actions workflow is included in `.github/workflows/deploy.yaml` to automatically publish this app to [sarcastichedgehog.com/buzzer](https://sarcastichedgehog.com/buzzer). If you'd like to adapt it:

- Ensure secrets `MULTISYNQ_API_KEY`, `MULTISYNQ_APP_ID`, and `GH_PAGES_DEPLOY_TOKEN` are set
- Adjust the `TARGET_DIR` if deploying to a different subfolder

> Note: You don’t need to use the workflow if running locally or deploying elsewhere. Just ensure `config.js` is present.

## 💡 Contributing

Fork the repo, modify the interface, enhance the logic, or replace the questions. All Vibe Coding enhancements welcome!

## 📜 License

MIT. Created by [Sarcastic Hedgehog](https://sarcastichedgehog.com).
