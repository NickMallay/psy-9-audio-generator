# psy-9-audio-generator

Python script that generates all 52 card audio files for the Psy-9 effect automatically.

## The problem it solves

Psy-9 needs a spoken audio file for every card in a standard deck. Doing that manually — paste text, generate audio, save file, rename file, repeat 51 more times — is exactly as tedious as it sounds. Change your wording once and you start over.

This script generates all 52 files in seconds. Adjust the prompt text, regenerate everything instantly.

## Video Demonstration 
[A video](https://www.youtube.com/watch?v=H3bCx-3aMz4) demonstration showing how much time is saved. 

## What it does

Builds a full deck by combining suits and values, constructs a prompt for each card with optional before/after text, generates audio via gTTS, and saves each file with a clean filename.

## Usage

Adjust the `before_prompt` and `after_prompt` variables to change the phrasing, then run the script. All 52 files land in `generated_audio/`.

## Part of a larger project

This tool supports the Psy-9 effect — a real-time, voice-based, AI-assisted magic trick. For the main system, see the [Psy-9 repo](https://github.com/NickMallay/Psy-9).
