# psy-9-audio-generator
What’s more magical than saving hours of work? This Python script automates audio file creation for the Psy-9 magic trick.

## Automating Audio File Generation for Psy 9: Saving Hours with Python

### Introduction
When I started my Psy 9 project, I had no idea I was walking into such a tedious mess. I needed 52 audio files — one for each playing card in a standard deck — and each one required copying text, generating audio with gTTS, saving it with the correct filename, and keeping everything organized. It was slow, clunky, and full of opportunities for mistakes. And all that was only for a single version of the effect.

After spending far too much time slogging through this process, I knew there had to be a better way. So, I built one. My Python script now generates all 52 files faster than I could manage to create just one by hand.

### The Problem
The manual process looked something like this:
1. Write the text for the card (e.g., "The Ace of Spades").
2. Paste it into a free text-to-speech site and generate an audio file.
3. Save the file with the correct filename.
4. Repeat this 51 more times — unless I decided to change my wording, in which case I’d have to start over.

I quickly realized that this wasn’t just inefficient — it was absurd. I needed automation.

### The Solution
I built a Python script to handle the entire process automatically. My goal was to make it flexible enough to adapt if my needs changed.

The script does four key things:

- **Deck Generation:** It builds a full deck of cards by combining suits and values in a loop.
- **Prompt Flexibility:** I added a feature that lets me add text before and after each card name. For example, I can produce prompts like *"The Ace of Spades is a powerful card"* without manually editing each one.
- **Audio Generation:** Using gTTS, the script creates audio files for each prompt.
- **File Management:** Each audio file is saved with a clean, organized filename to keep things tidy.

Here’s the core logic that powers the whole thing:

```python
from gtts import gTTS

def build_deck(suits, values):
    return [f"{value} of {suit}" for suit in suits for value in values]

def build_list_of_prompts(deck, before_prompt="", after_prompt=""):
    return [f"{before_prompt.strip()} {card} {after_prompt.strip()}" for card in deck]

def convert_to_audio(deck, prompts):
    for card, prompt in zip(deck, prompts):
        tts = gTTS(prompt)
        filename = f"generated_audio/{card.replace(' ', '_')}.mp3"
        tts.save(filename)
```

### The Outcome
The difference was huge. Instead of spending hours copying text and saving files one by one, I could now generate all 52 audio files in seconds. Better yet, I knew that when the MVP was done, I was going to want multiple versions of the effect. With this script, I could just adjust the prompt text in my code and regenerate everything instantly.

### The Video Demonstration
To illustrate the difference, I recorded a short video comparing both approaches:
1. First, I attempt to manually create an audio file by navigating a free TTS website, dealing with its intrusive ads, generating the file, and renaming it.
2. Then, I use my Python script to generate all 52 files — faster than I could manually create one.

[![Watch the Video](https://img.youtube.com/vi/VIDEO_ID/maxresdefault.jpg)](https://youtu.be/H3bCx-3aMz4)

The side-by-side comparison makes it clear just how much time automation saved me.

### The Takeaway
This project wasn’t just about saving time — it was a breakthrough for me. It was the first time I applied my programming skills to solve a real-world problem without guidance. More importantly, it gave me the confidence to believe that I can build solutions when I need them.

I also learned that small bits of automation can feel like superpowers. What seemed like an unavoidable chore turned into an opportunity to make my life easier.

### Next Steps
I'm thinking about a few ways to improve the script:
- Adding command-line arguments for custom prompts and output directories.
- Creating a simple GUI to make it accessible for non-coders.
- Organizing the audio files into folders by suit for better structure.

### Final Thoughts
This wasn’t my biggest project, but it’s one I’m especially proud of. It reminded me that programming doesn’t have to be flashy or complex to be powerful — sometimes the best code is just the kind that makes your life easier.

