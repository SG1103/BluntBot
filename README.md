# BluntBot - AI Speech-to-Speech Prototype

This is a quick prototype built in 2 days using **React JS** and the latest **AI tools**.

## What Makes This Different?

Unlike normal AI agents, which convert speech to text, process the text in a text-based model, and then convert it back into speech, this prototype enables **speech-to-speech** conversations. This approach allows for:

- **Faster response times**
- **Understanding of user emotions**
- **Handling interruptions** (Try changing the mode to test it out)

## Features

Currently, this AI acts as a personal assistant (PA) with a **rude** way of speaking, showcasing the different styles it can adapt for various use cases. Here's how you can interact with it:

1. **Press "Connect" to start**.
2. You can use it in two modes:
   - **Press to Speak**: Press a button to speak.
   - **Conversational Mode**: Speak naturally without pressing a button. You can also interrupt it mid-sentence.

## What Can You Do?

Feel free to explore the AI's capabilities:

- Speak with it in **different languages**.
- **Ask about me (Saad)**.
- **Ask it to speak in different accents** (It's not perfect, but improving).

---

### Note
This is still a work in progress, so some features (like accents) may not work as well as intended.




# OpenAI Realtime Console

The OpenAI Realtime Console is intended as an inspector and interactive API reference
for the OpenAI Realtime API. It comes packaged with two utility libraries,
[openai/openai-realtime-api-beta](https://github.com/openai/openai-realtime-api-beta)
that acts as a **Reference Client** (for browser and Node.js) and
[`/src/lib/wavtools`](./src/lib/wavtools) which allows for simple audio
management in the browser.

<img src="/readme/realtime-console-demo.png" width="800" />

# Starting the console

This is a React project created using `create-react-app` that is bundled via Webpack.
Install it by extracting the contents of this package and using;

```shell
$ npm i
```

Start your server with:

```shell
$ npm start
```

It should be available via `localhost:3000`.

# Table of contents

1. [Using the console](#using-the-console)
   1. [Using a relay server](#using-a-relay-server)
1. [Realtime API reference client](#realtime-api-reference-client)
   1. [Sending streaming audio](#sending-streaming-audio)
   1. [Adding and using tools](#adding-and-using-tools)
   1. [Interrupting the model](#interrupting-the-model)
   1. [Reference client events](#reference-client-events)
1. [Wavtools](#wavtools)
   1. [WavRecorder quickstart](#wavrecorder-quickstart)
   1. [WavStreamPlayer quickstart](#wavstreamplayer-quickstart)
1. [Acknowledgements and contact](#acknowledgements-and-contact)

# Using the console

The console requires an OpenAI API key (**user key** or **project key**) that has access to the
Realtime API. You'll be prompted on startup to enter it. It will be saved via `localStorage` and can be
changed at any time from the UI.

To start a session you'll need to **connect**. This will require microphone access.
You can then choose between **manual** (Push-to-talk) and **vad** (Voice Activity Detection)
conversation modes, and switch between them at any time.

There are two functions enabled;

- `get_weather`: Ask for the weather anywhere and the model will do its best to pinpoint the
  location, show it on a map, and get the weather for that location. Note that it doesn't
  have location access, and coordinates are "guessed" from the model's training data so
  accuracy might not be perfect.
- `set_memory`: You can ask the model to remember information for you, and it will store it in
  a JSON blob on the left.

You can freely interrupt the model at any time in push-to-talk or VAD mode.
