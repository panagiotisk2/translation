Two-Way Voice Translator – HTML Prototype
This is a proof-of-concept for a real-time two-way voice translation app.

It demonstrates:

Speech-to-text (STT) using the Web Speech API.

Translation using OpenAI's API (optional).

Text-to-speech (TTS) using the Web Speech Synthesis API.

A UI for selecting languages for two speakers and translating in both directions.

Features
Two-way conversation mode (Speaker A → Speaker B and vice versa).

Language selection for each speaker.

Detects when a speaker finishes talking and automatically triggers translation.

Translated text is spoken back to the other user.

Works locally without API key (passthrough mode for testing).

Optional: Uses OpenAI GPT model for real translations.

Requirements
Browser: Chrome (recommended) or Edge with microphone access enabled.

Microphone: Required for speech recognition.

Internet connection: Required only if using OpenAI API for translations.

How to Use
Download and open twoway-voice-translate.html in Chrome.

Allow microphone access when prompted.

Choose languages for each speaker.

Press Start A or Start B to begin listening for that speaker.

Speak clearly, then pause — the app will transcribe, translate, and speak back.

Use Stop All to stop recognition and TTS.

Optional: Enable Real Translation
Get an OpenAI API key.

Paste it in the "OpenAI API Key" field at the top of the page.

Keep model name as gpt-4o-mini (or change to any suitable translation-capable model).

Now, when you speak, the app will send the transcript to OpenAI for translation.

Technical Notes
STT: Uses SpeechRecognition / webkitSpeechRecognition.

TTS: Uses speechSynthesis and tries to match a voice to the target locale.

Translation API: Calls POST https://api.openai.com/v1/chat/completions with a translator system prompt.

Fallback mode (no API key) simply returns the same text so you can test the UX without network calls.

Limitations
Browser support for Web Speech API varies; best results in Chrome on desktop.

Web Speech API is not truly real-time streaming — it processes after speech segments.

Voice detection relies on pause detection; noisy environments may affect results.

Next Steps
Integrate a more robust VAD (Voice Activity Detection) for better turn-taking.

Add streaming STT/TTS for lower latency.

Wrap in React Native or Flutter for mobile deployment.
