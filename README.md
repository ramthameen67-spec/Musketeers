# 🕶️ Coolkid Client

A neon-red, single-file AI client that runs entirely in your browser. Chat, generate code, make images, talk on a voice call, and generate playable games from a text prompt, all powered by the Google Gemini API using **your own API keys**.

No backend, no build step, no dependencies. Just one `index.html`.

## Features

- **Chatbot**: conversational AI with saved chats, personal context ("About you"), and selectable talking styles (Chill, Hype, Serious, Short).
- **Code mode**: code-focused assistant. Code blocks get a **Copy** button, and HTML blocks get a **Run ▶** button that previews them in a sandboxed iframe.
- **Games**: describe a game (or pick Neon Snake, Pong vs AI, Flappy Ghost, Space Shooter, Tic-Tac-Toe vs AI, Memory Match) and it generates a self-contained HTML game that runs in a sandboxed frame.
- **Image generation**: say "draw a ...", use `/image ...`, or toggle *Create image*. Falls back to an SVG drawing if no image model is available on your keys.
- **Voice**: spoken replies with 5 male voices (Puck, Charon, Fenrir, Orus, Iapetus), plus a hands-free **call mode** using speech recognition.
- **Attachments**: camera, photos, and files (images, audio, video, PDFs, and text; up to 15 MB each).
- **Model picker**: Coolkid 3.2 to 4 presets plus direct Gemini models, with Low/Medium/High effort and a "Think harder" toggle.
- **Exact calculator**: type any arithmetic (e.g. `73196491+83719471×8371993÷819`) and it is solved instantly with big-number fractions, so there are no guesses or rounding errors. Word problems use Gemini code execution.
- **Long-term memory**: Coolkid saves lasting facts you tell it (or say "remember that...") and uses them in every chat. View, edit, or delete them in **Settings → Memory**.
- **Gemini 4**: **Coolkid 4 Argon** runs on `gemini-4-argon`, Google's newest flagship model. It needs a key with billing; on a free key the app falls back to a Flash model automatically.
- **Web search**: tap **+ → Search the web** (or ask about news, prices, weather, scores, and so on) and answers are grounded in Google Search, with source links under the reply.
- **Thinking timer**: while waiting you see "Thinking for 12s", and each reply ends with "Thought for 12s".
- **Fast mode**: Coolkid 3.5 Smart defaults to the **Fast** effort level (limited thinking). Pick Medium or High in the effort menu for deeper answers.
- **Multi-key rotation**: add up to 3 API keys; requests rotate between them and skip keys that fail or hit limits.
- **Local accounts**: multiple profiles stored on your device, with chat export to JSON.

## Quick start

1. Download `index.html` (or clone this repo).
2. Open it in a modern browser (Chrome, Edge, or Safari recommended).
3. Create an account (this is local to your browser only).
4. Open **Settings** and paste in at least one Gemini API key. Free keys are available at [aistudio.google.com/apikey](https://aistudio.google.com/apikey).
5. Start chatting.

### Host it on GitHub Pages

1. Push `index.html` and `README.md` to a repository.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
4. Your client will be live at `https://<your-username>.github.io/<repo-name>/`.

## Notes on API keys and models

- The "Pro-class" presets (Coolkid 3.8, 3.7, 3.6, and 3.1 Pro) need a key with billing enabled. On a free key they automatically fall back to a Flash model.
- Model IDs are defined near the top of the script (`MODELS`, `M`, `FALL`). If Google renames or retires a model, edit them there.
- Voice calls need speech recognition support (Chrome, Edge, or Safari) and microphone permission.

## Privacy and security

- Everything (accounts, chats, settings, API keys) is stored in your browser's `localStorage`. Nothing is sent anywhere except directly to Google's Gemini API.
- Passwords are hashed in the browser, but this is a **convenience profile switcher, not real security**. Anyone with access to your browser profile can read stored data, including your API keys.
- **Never commit API keys** to the repository or hard-code them into the file. Use restricted keys and avoid using this on shared computers.
- Generated games and code previews run in sandboxed iframes (`allow-scripts` only), but only run code you trust.

## Tech

Vanilla HTML, CSS, and JavaScript in a single file. Uses the Gemini `generateContent` REST API, the Web Speech API, `localStorage`, and `SubtleCrypto`.

## Project structure

```
.
├── index.html   # the entire app
└── README.md
```

## Contributing

Issues and pull requests are welcome. Since the whole app is one file, keep changes small and focused.

## License

Add a license of your choice (for example, [MIT](https://choosealicense.com/licenses/mit/)) by creating a `LICENSE` file.
