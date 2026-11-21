<p align="center"><img src="https://emkay.ai/icon.svg" width="120" alt=""></p>

<h1 align="center">Emkay</h1>

<p align="center"><b>A stock <a href="https://openvoiceos.org">OpenVoiceOS</a> voice assistant, running in your browser.</b><br>
Phone, tablet, TV or a Raspberry Pi in kiosk mode – nothing to install.</p>

<p align="center"><a href="https://app.emkay.ai/"><b>Open Emkay</b></a> · <a href="https://emkay.ai/">emkay.ai</a> · <a href="https://emkay.ai/home/">Emkay Home</a> · <a href="https://store.emkay.ai/">Skill store</a> · <a href="https://dev.emkay.ai/">Emkay Dev</a> · <a href="https://github.com/emkay-voice/emkay">Source</a> · <a href="https://huggingface.co/Emkay-Voice">Models</a></p>

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

**Status: early alpha.** Twelve languages. On-device speech recognition and voices, Emkay's own
wake word "Hey Emkay", skills from the control panel and the store. Emkay can think in three
places – ⚙ → *Where should Emkay think?*: on the device, in the house with **Emkay Home**
(HiveMind), or with **Home Assistant** (an Assist satellite). Short, current facts come from
Wikidata, the horoscope and the OpenVoiceOS blog are read aloud, and Emkay has started making
music: it sings – autotuned onto the melody, with a band behind it – plays karaoke, and leads a
jam band by voice, all made on the device.

### Home Assistant

⚙ → *Where should Emkay think?* → *Connect to my Home Assistant*: one login on Home Assistant's
own page, no token. Lights and heating by voice through Assist, and Emkay shows up in Home
Assistant as a device of its own – volume, listening on and off, "say", its control panel's
settings. With Emkay Home, the house and every Emkay in it. On the Home Assistant side it is the
[OpenVoiceOS integration](https://github.com/andlo/ha-ovos-integration), which works for any
OpenVoiceOS.

## Repositories

### The app

| Repository | What it is |
|---|---|
| [emkay](https://github.com/emkay-voice/emkay) | the app: OpenVoiceOS in the browser, served at [app.emkay.ai](https://app.emkay.ai/) |
| [emkay-home](https://github.com/emkay-voice/emkay-home) | Emkay Home, the OpenVoiceOS for the house – every Emkay can be its satellite; one line installs it, a QR code adds a device ([emkay.ai/home](https://emkay.ai/home/)) |
| [store](https://github.com/emkay-voice/store) | the Emkay skill store, [store.emkay.ai](https://store.emkay.ai/) – complete, working skills only, tested every night, installed straight into your Emkay |
| [emkay-voice.github.io](https://github.com/emkay-voice/emkay-voice.github.io) | the project page, [emkay.ai](https://emkay.ai/) |

### Emkay Dev – make a skill

| Repository | What it is |
|---|---|
| [dev](https://github.com/emkay-voice/dev) | [dev.emkay.ai](https://dev.emkay.ai/): make an OpenVoiceOS skill in the browser and hear Emkay answer it, step by step |
| [vscode-emkay](https://github.com/emkay-voice/vscode-emkay) | Emkay Dev for VS Code: Emkay next to your code, also in vscode.dev – new skill, run, test, add a language |
| [ovos-routing-judge](https://github.com/emkay-voice/ovos-routing-judge) | who took an utterance, and was it the right skill? – the judge behind Emkay Dev's and the store's tests |

Templates, each in all of Emkay's languages – start from one in *Emkay: New skill*, or use it as a GitHub template:

| Repository | What it shows |
|---|---|
| [ovos-skill-hello-example](https://github.com/emkay-voice/ovos-skill-hello-example) | your first skill: say "hello from my skill" and it answers |
| [ovos-skill-quiz-example](https://github.com/emkay-voice/ovos-skill-quiz-example) | a quiz that keeps score – `get_response`, `ask_yesno` and stop |
| [ovos-skill-pictures-example](https://github.com/emkay-voice/ovos-skill-pictures-example) | pictures on the screen – "show me a dog" |
| [ovos-skill-air-quality-example](https://github.com/emkay-voice/ovos-skill-air-quality-example) | asking the web: air quality and UV where you are (Open-Meteo, no key) |
| [ovos-skill-answers-example](https://github.com/emkay-voice/ovos-skill-answers-example) | your own answers – a common query skill from a list of questions |
| [ovos-skill-radio-example](https://github.com/emkay-voice/ovos-skill-radio-example) | your own radio – stations played with the media player (OCP) |
| [ovos-skill-hints-example](https://github.com/emkay-voice/ovos-skill-hints-example) | a fallback skill that suggests the sentence you may have meant |
| [ovos-skill-common-reading-example](https://github.com/emkay-voice/ovos-skill-common-reading-example) | a reading provider: RSS and HTML scraping, caching, translation |
| [ovos-phal-plugin-quiet-hours-example](https://github.com/emkay-voice/ovos-phal-plugin-quiet-hours-example) | a PHAL plugin: the voice down in the evening, up in the morning |

### OVOS plugins (made for Emkay, usable anywhere)

| Repository | What it is |
|---|---|
| [ovos-phal-plugin-browser](https://github.com/emkay-voice/ovos-phal-plugin-browser) | the browser tab as the device: volume, location, power, connectivity, sensors, camera |
| [ovos-audio-plugin-browser](https://github.com/emkay-voice/ovos-audio-plugin-browser) | audio backend: music, radio and podcasts in the browser's `<audio>` element |
| [ovos-stt-plugin-whisper-browser](https://github.com/emkay-voice/ovos-stt-plugin-whisper-browser) | Whisper speech recognition on the device, in the browser – audio never leaves it |
| [ovos-stt-plugin-browser](https://github.com/emkay-voice/ovos-stt-plugin-browser) | the browser's own speech recognition (Web Speech API) |
| [ovos-tts-plugin-piper-browser](https://github.com/emkay-voice/ovos-tts-plugin-piper-browser) | Piper voices made on the device, in the browser |
| [ovos-assist-pipeline-plugin](https://github.com/emkay-voice/ovos-assist-pipeline-plugin) | intent pipeline: what Home Assistant's Assist recognizes (lights, heating, rooms) goes to Home Assistant |
| [ovos-phal-plugin-ha-link](https://github.com/emkay-voice/ovos-phal-plugin-ha-link) | links an OpenVoiceOS device to Home Assistant from the device's side – its bus and control panel, no open ports, works behind NAT |
| [ovos-phal-plugin-midi](https://github.com/emkay-voice/ovos-phal-plugin-midi) | a MIDI instrument on the bus: a General MIDI synth skills play note by note, MIDI keyboards in, real instruments out |
| [ovos-ocp-tts-plugin](https://github.com/emkay-voice/ovos-ocp-tts-plugin) | text read aloud as media: `tts//` uris play as sentences in the device's own voice ([ovos-media#240](https://github.com/OpenVoiceOS/ovos-media/issues/240)) |
| [ovos-network-log](https://github.com/emkay-voice/ovos-network-log) | a network log for any OpenVoiceOS: every request – when, where, who asked, never what |
| [ovos-PHAL-plugin-netpolicy](https://github.com/emkay-voice/ovos-PHAL-plugin-netpolicy) | per-service network policy, including enforced Tor routing (design stage) |

### OVOS skills

| Repository | What it is |
|---|---|
| [ovos-skill-about-emkay](https://github.com/emkay-voice/ovos-skill-about-emkay) | who Emkay is and where it comes from – Mycroft's Mark 1 and Mark 2, OpenVoiceOS |
| [ovos-skill-guardian](https://github.com/emkay-voice/ovos-skill-guardian) | your privacy by voice: what went out today, who hears you, going offline |
| [ovos-skill-store](https://github.com/emkay-voice/ovos-skill-store) | find and install skills by voice, from one or more skill stores |
| [ovos-skill-kiosk](https://github.com/emkay-voice/ovos-skill-kiosk) | full screen, screen kept on and install as an app, by voice |
| [ovos-skill-wikidata](https://github.com/emkay-voice/ovos-skill-wikidata) | short, current facts from Wikidata – who leads a country, capitals, population, birthdays, where places are; no keys |
| [ovos-skill-wiki-offline](https://github.com/emkay-voice/ovos-skill-wiki-offline) | fully offline general knowledge: Wikipedia's ~10,000 vital articles |
| [ovos-skill-karaoke](https://github.com/emkay-voice/ovos-skill-karaoke) | the device sings – its own voice autotuned onto the melody, with a band – or plays karaoke, with words and chords on the screen |
| [ovos-skill-jamband](https://github.com/emkay-voice/ovos-skill-jamband) | a band you lead with your voice: drums, then bass, then the whole band, in any style and key |
| [ovos-skill-music-teacher](https://github.com/emkay-voice/ovos-skill-music-teacher) | piano, guitar and bass lessons: it shows you, plays it, listens to you play and tells you what was right; a tuner, and a course per instrument |
| [ovos-skill-intercom](https://github.com/emkay-voice/ovos-skill-intercom) | spoken messages to another OVOS device in the house, with a spoken reply |
| [ovos-skill-nato-alphabet](https://github.com/emkay-voice/ovos-skill-nato-alphabet) | spells words with the NATO alphabet – Alpha, Bravo, Charlie… |
| [ovos-skill-morse-code](https://github.com/emkay-voice/ovos-skill-morse-code) | text to and from Morse code, played as beeps |

### Stories and reading

Providers for the [common reading pipeline](https://github.com/OpenVoiceOS/ovos-common-reading-pipeline-plugin): "read me a fairy tale" and so on.

| Repository | What it reads |
|---|---|
| [ovos-skill-andersen-tales](https://github.com/emkay-voice/ovos-skill-andersen-tales) | Hans Christian Andersen's fairy tales |
| [ovos-skill-grimm-tales](https://github.com/emkay-voice/ovos-skill-grimm-tales) | the Brothers Grimm's fairy tales |
| [ovos-skill-andrew-lang-tales](https://github.com/emkay-voice/ovos-skill-andrew-lang-tales) | Andrew Lang's Fairy Books |
| [ovos-skill-bechstein-tales](https://github.com/emkay-voice/ovos-skill-bechstein-tales) | Ludwig Bechstein's German fairy tales (German) |
| [ovos-skill-cosquin-tales](https://github.com/emkay-voice/ovos-skill-cosquin-tales) | Emmanuel Cosquin's Lorraine folk tales (French) |
| [ovos-skill-365tomorrows-stories](https://github.com/emkay-voice/ovos-skill-365tomorrows-stories) | daily flash sci-fi from 365tomorrows.com |
| [ovos-skill-voices-of-tomorrow](https://github.com/emkay-voice/ovos-skill-voices-of-tomorrow) | 365tomorrows' *Voices of Tomorrow* audio readings (a media skill) |
| [ovos-skill-arxiv-papers](https://github.com/emkay-voice/ovos-skill-arxiv-papers) | arXiv paper abstracts |
| [ovos-skill-horoscope-readings](https://github.com/emkay-voice/ovos-skill-horoscope-readings) | the daily horoscope, in any language |
| [ovos-skill-opds-books](https://github.com/emkay-voice/ovos-skill-opds-books) | books from e-book catalogs (OPDS, Standard Ebooks) |
| [ovos-skill-documents](https://github.com/emkay-voice/ovos-skill-documents) | your own documents – text, Markdown, PDF, Word, OpenDocument, EPUB and HTML – from folders or urls |

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
