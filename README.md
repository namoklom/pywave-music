# Pywave - Python-based Music Player

## 👤 Author

| Name            | Role              | LinkedIn                                      |
|-----------------|-------------------|-----------------------------------------------|
| Jason Emmanuel  | Python Developer | [linkedin.com/in/jasoneml](https://www.linkedin.com/in/jasoneml/) |

Pywave is a lightweight, user-friendly music player built using Python. Designed with simplicity and modularity in mind, Pywave allows users to browse and play local `.mp3` music files effortlessly through an intuitive command-line interface.

---

## 🔍 Overview

Pywave showcases the power and flexibility of Python in developing real-world applications. By leveraging modules like `IPython.display` and `os`, Pywave offers a clean and functional way to interact with a local music library.

Whether you're a Python enthusiast or a casual listener, Pywave helps you enjoy your favorite tracks with just a few lines of code.

---

## 🚀 Features

- 🎶 **Browse Music Library**: Lists all `.mp3` files from a user-defined folder.
- ▶️ **Play Music**: Instantly play a selected track using its index.
- 💬 **Interactive CLI**: Simple command-line prompts guide the user through track selection.
- 🧩 **Modular & Extensible**: Easy to add new features like playlists, shuffle mode, or even streaming support.

---

## 🛠 How It Works

### 1. Initialization
When the `MusicPlayer` class is instantiated, it loads all `.mp3` files from the specified folder path (default is `/content/sample_data`).

### 2. Display Music List
Using the `display_music_list()` method, Pywave lists all available tracks with corresponding indices.

### 3. Play Selected Track
With the `play_music(index)` method, users can play a track by entering its number. The selected file is played using the IPython `Audio` widget with autoplay enabled.

---

## 🧾 Code Example

```python
from IPython.display import Audio, display
import os

class MusicPlayer:
    def __init__(self, music_folder_path="/content/sample_data"):
        self.music_folder_path = music_folder_path
        self.music_files = [file for file in os.listdir(music_folder_path) if file.endswith(".mp3")]

    def display_music_list(self):
        print("** Welcome to Pywave **")
        print("Music List:")
        for i, music_file in enumerate(self.music_files, start=1):
            print(f"{i}. {music_file}")

    def play_music(self, index):
        if 1 <= index <= len(self.music_files):
            music_file = self.music_files[index - 1]
            music_path = os.path.join(self.music_folder_path, music_file)
            display(Audio(filename=music_path, autoplay=True))
        else:
            print("Invalid index.")

# Usage
player = MusicPlayer()
player.display_music_list()
music_index = int(input("Select a music number to play: "))
player.play_music(music_index)
```

## 🧰 Tools & Libraries Used

| Tool / Library       | Description                                                    |
|----------------------|----------------------------------------------------------------|
| `Python`             | The core programming language used for the entire application  |
| `os`                 | Used to interact with the file system and list `.mp3` files    |
| `IPython.display`    | Provides the `Audio` widget to play music within notebooks     |
| `Jupyter Notebook`   | Ideal runtime environment for interactive use of Pywave        |
