# SpeakSharp — AI Speaking Coach

A local, single-file web app that helps you practice and improve impromptu speaking, interview answers, and structured communication using Claude AI as your coach.

![SpeakSharp Screenshot](screenshot.png)

## What it does

- **Record your voice** — mic input with live volume monitor
- **Live transcript** — real-time speech-to-text as you speak
- **Pause detection** — classifies micro (<1s), natural (1–3s), and long (>3s) pauses inline in your transcript
- **Filler word highlighting** — catches um, uh, like, basically, actually, and more
- **AI feedback via Claude** — scores structure, fluency, clarity, and overall; gives vocabulary upgrades, framework adherence, and an honest verdict
- **PREP / STAR framework** — choose your structure before each response
- **Progress tracking** — session history, score trend, filler totals across the session
- **Audio playback** — listen back to every response

## Requirements

- **Chrome** (required — Safari does not support the Web Speech API reliably)
- **Python 3** (to run a local server — needed for mic access)
- **Anthropic API key** — get one free at [console.anthropic.com](https://console.anthropic.com)

## Setup

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/speaksharp.git
cd speaksharp

# 2. Start a local server
python3 -m http.server 8080

# 3. Open in Chrome
# http://localhost:8080
```

## API Key

Your Anthropic API key is entered in the **Settings** tab inside the app.

- It is stored **in memory only** (JavaScript variable)
- It is **never written to disk**, never committed to git, never sent anywhere except Anthropic's API
- It clears automatically when you close the tab

**Never hardcode your API key into the source file.**

## How to use

1. Pick a **Mode** — Impromptu (random topic) or Interview (behavioural questions)
2. Pick a **Framework** — PREP or STAR
3. Read the question
4. Click the **record button** and speak your answer
5. Click again to stop
6. Click **Analyze Response** for Claude's feedback

## Privacy

- Audio is recorded locally in your browser and never uploaded
- Transcripts are sent to Anthropic's API only when you click Analyze
- No data is stored between sessions

## Browser Support

| Browser | Recording | Transcription |
|---------|-----------|---------------|
| Chrome  | ✅        | ✅            |
| Safari  | ✅        | ❌ (Web Speech API not supported) |
| Firefox | ✅        | ❌ (Web Speech API not supported) |
| Edge    | ✅        | ✅ (Chromium-based) |

## Tech stack

- Vanilla HTML / CSS / JavaScript — zero dependencies, zero build step
- [Web Speech API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API) — transcription
- [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) — pause detection
- [MediaRecorder API](https://developer.mozilla.org/en-US/docs/Web/API/MediaRecorder) — audio capture
- [Anthropic Claude API](https://docs.anthropic.com) — AI feedback

## Roadmap ideas

- [ ] Whisper API integration for Safari/Firefox support
- [ ] Persistent progress across sessions (localStorage)
- [ ] Custom question banks
- [ ] Export feedback as PDF
- [ ] Speaking pace graph over time

## License

MIT
