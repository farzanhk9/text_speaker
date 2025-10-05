# 🗣️ Text to Speech CLI Tool
# Author: YourName
# License: MIT

from gtts import gTTS
import os

def text_to_speech():
    print("🎤 Welcome to Text Speaker!")
    print("Type something to convert it to speech.\n")

    text = input("📝 Enter text: ").strip()
    if not text:
        print("⚠️ No text entered. Exiting.")
        return

    language = "en"
    tts = gTTS(text=text, lang=language, slow=False)

    filename = "output.mp3"
    tts.save(filename)

    print(f"✅ Audio saved as {filename}")
    play = input("▶️ Play now? (y/n): ").lower()
    if play == "y":
        os.system(f"start {filename}")

if __name__ == "__main__":
    text_to_speech()

