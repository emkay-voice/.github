<p align="center"><img src="https://emkay.ai/icon.svg" width="120" alt=""></p>

<h1 align="center">Emkay</h1>

<p align="center"><b>A stock <a href="https://openvoiceos.org">OpenVoiceOS</a> voice assistant, running in your browser.</b><br>
Phone, tablet, TV or a Raspberry Pi in kiosk mode – nothing to install.</p>

<p align="center"><a href="https://app.emkay.ai/"><b>Open Emkay</b></a> · <a href="https://emkay.ai/">emkay.ai</a> · <a href="https://store.emkay.ai/">Skill store</a> · <a href="https://github.com/emkay-voice/emkay">Source</a> · <a href="https://huggingface.co/Emkay-Voice">Models</a></p>

---

## What Emkay is

Emkay is OpenVoiceOS – core, skills, the GUI and the OVOS control panel – compiled to WebAssembly
with [Pyodide](https://pyodide.org) and running inside a web page. Open a link, and the phone, tablet
or TV in front of you is a voice assistant, with the animated face from the Mycroft Mark II
Kickstarter ([ovos-gui-visage](https://github.com/OscillateLabsLLC/ovos-gui-visage)) as its screen.
No app store, no sideloading.

The browser is the hardware: microphone, speaker, location, sensors and camera each answer OVOS the
way a device's PHAL plugin does. Everything else is the same OpenVoiceOS an
[ovos-installer](https://github.com/OpenVoiceOS/ovos-installer) device gets – same skills, same
intent pipeline, same settings – and skills install the usual way.

**"Emkay" is "MK" said out loud**, a nod to Mycroft's Mark I and Mark II.

### Close to OVOS

Emkay is built on and inspired by OpenVoiceOS, and stays as close to stock as it can. Where the
browser needs something a device does not, it is done the OVOS way: as an ordinary plugin or skill
in its own repository, named like any other OVOS package, that anyone can use outside Emkay.
Skills only send bus messages; a PHAL plugin does the device part, so the same features can come to
other hardware.

### Privacy built in

- **Network log** – everything Emkay contacts, by day and service, viewable and downloadable from the menu.
- **Local only** – "go offline" and speech recognition and voice run on the device; nothing you say leaves it.
- **On-device speech** – Whisper speech recognition and Piper voices in the browser (WebAssembly/WebGPU).
- **Ask it** – "what went out today?" answers from the log, by voice.

**Status: early alpha.** Twelve languages, English first. Skills installable from the control panel
and the store, wake word, and on-device speech. Next up: Emkay's own wake word "hey M K", a
satellite mode (HiveMind, then Home Assistant Assist), and self-hosting Emkay from your own house.

## Repositories

### The app

| Repository | What it is |
|---|---|
| [emkay](https://github.com/emkay-voice/emkay) | the app: OpenVoiceOS in the browser, served at [app.emkay.ai](https://app.emkay.ai/) |
| [store](https://github.com/emkay-voice/store) | the Emkay skill store, [store.emkay.ai](https://store.emkay.ai/) – complete, working skills only, installed straight into your Emkay |
| [emkay-voice.github.io](https://github.com/emkay-voice/emkay-voice.github.io) | the project page, [emkay.ai](https://emkay.ai/) |

### OVOS plugins (made for Emkay, usable anywhere)

| Repository | What it is |
|---|---|
| [ovos-phal-plugin-browser](https://github.com/emkay-voice/ovos-phal-plugin-browser) | the browser tab as the device: volume, location, power, connectivity, sensors, camera |
| [ovos-audio-plugin-browser](https://github.com/emkay-voice/ovos-audio-plugin-browser) | audio backend: music, radio and podcasts in the browser's `<audio>` element |
| [ovos-stt-plugin-whisper-browser](https://github.com/emkay-voice/ovos-stt-plugin-whisper-browser) | Whisper speech recognition on the device, in the browser – audio never leaves it |
| [ovos-stt-plugin-browser](https://github.com/emkay-voice/ovos-stt-plugin-browser) | the browser's own speech recognition (Web Speech API) |
| [ovos-tts-plugin-piper-browser](https://github.com/emkay-voice/ovos-tts-plugin-piper-browser) | Piper voices made on the device, in the browser |

### OVOS skills

| Repository | What it is |
|---|---|
| [ovos-skill-about-emkay](https://github.com/emkay-voice/ovos-skill-about-emkay) | who Emkay is and where it comes from – Mycroft's Mark 1 and Mark 2, OpenVoiceOS |
| [ovos-skill-guardian](https://github.com/emkay-voice/ovos-skill-guardian) | your privacy by voice: what went out today, who hears you, going offline |
| [ovos-skill-store](https://github.com/emkay-voice/ovos-skill-store) | find and install skills by voice, from one or more skill stores |
| [ovos-skill-kiosk](https://github.com/emkay-voice/ovos-skill-kiosk) | full screen, screen kept on and install as an app, by voice |

### Models and training

| Repository | What it is |
|---|---|
| [stt-models](https://github.com/emkay-voice/stt-models) | speech recognition models per language, converted to ONNX for the browser – and why each language uses its model (e.g. a national Danish model) |
| [hey-emkay-wakeword](https://github.com/emkay-voice/hey-emkay-wakeword) | training "hey M K", Emkay's own wake word (openWakeWord, Colab notebook) |

Converted models are published on Hugging Face: [Emkay-Voice](https://huggingface.co/Emkay-Voice).

### Hardware

| Repository | What it is |
|---|---|
| [emkay-capsule](https://github.com/emkay-voice/emkay-capsule) | a 3D-printable shell that stands a phone upright as an Emkay speaker, inspired by the 2018 Mark II Kickstarter concept (concept stage) |

## Thanks

Emkay stands on the shoulders of [Mycroft AI](https://mycroft.ai) and the
[OpenVoiceOS](https://openvoiceos.org) community. It is a community project under Apache-2.0 –
issues, ideas and pull requests are welcome in any of the repositories above.
