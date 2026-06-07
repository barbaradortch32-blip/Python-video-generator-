# Python Video Generator

A comprehensive open-source Python video generator with all features built using free and open-source libraries.

## Features

- **Video Composition** - Combine multiple video clips
- **Text Overlays** - Add dynamic text to videos
- **Transitions & Effects** - Smooth transitions and visual effects
- **Audio Mixing** - Mix and manage multiple audio tracks
- **Image to Video** - Convert image sequences to video
- **MP4 Export** - High-quality MP4 output

## Installation

### Prerequisites

- Python 3.8+
- FFmpeg (required for video processing)

### Install FFmpeg

**Windows:**
```bash
choco install ffmpeg
```

**macOS:**
```bash
brew install ffmpeg
```

**Linux (Ubuntu/Debian):**
```bash
sudo apt-get install ffmpeg
```

### Install Python Dependencies

```bash
git clone https://github.com/barbaradortch32-blip/Python-video-generator-.git
cd Python-video-generator-
pip install -r requirements.txt
```

## Quick Start

### 1. Create a Simple Video from Images

```python
from src.video_generator import VideoGenerator

generator = VideoGenerator(fps=30, width=1920, height=1080)
generator.create_video_from_images(
    image_folder='images/',
    output_path='output/video.mp4',
    duration_per_image=2
)
```

### 2. Compose Multiple Video Clips

```python
from src.video_composer import VideoComposer

composer = VideoComposer()
composer.add_clip('videos/clip1.mp4')
composer.add_clip('videos/clip2.mp4')
composer.add_clip('videos/clip3.mp4')
composer.export('output/composed.mp4')
```

### 3. Add Text Overlays

```python
from src.text_overlay import TextOverlay

overlay = TextOverlay('videos/input.mp4')
overlay.add_text(
    text='Hello World',
    position='center',
    duration=(0, 5),
    font_size=50
)
overlay.export('output/with_text.mp4')
```

### 4. Apply Transitions & Effects

```python
from src.effects import Effects

effects = Effects('videos/input.mp4')
effects.add_fade_in(duration=1)
effects.add_fade_out(duration=1)
effects.export('output/with_effects.mp4')
```

### 5. Mix Audio Tracks

```python
from src.audio_mixer import AudioMixer

mixer = AudioMixer()
mixer.add_video('videos/video.mp4')
mixer.add_audio('audio/background_music.mp3', volume=0.5)
mixer.add_audio('audio/voiceover.mp3', volume=0.8)
mixer.export('output/mixed_audio.mp4')
```

## Project Structure

```
Python-video-generator-/
├── src/
│   ├── __init__.py
│   ├── video_generator.py      # Core video generation
│   ├── video_composer.py       # Compose multiple clips
│   ├── text_overlay.py         # Add text to videos
│   ├── effects.py              # Transitions and effects
│   ├── audio_mixer.py          # Audio mixing
│   └── utils.py                # Utility functions
├── examples/
│   ├── example_compose.py
│   ├── example_text.py
│   ├── example_effects.py
│   ├── example_audio.py
│   └── example_images_to_video.py
├── tests/
│   ├── test_video_generator.py
│   ├── test_composer.py
│   └── test_effects.py
├── requirements.txt
├── setup.py
└── README.md
```

## Dependencies

All dependencies are free and open-source:

- **moviepy** - Video composition and editing
- **ffmpeg-python** - Python FFmpeg wrapper
- **pillow** - Image processing
- **numpy** - Numerical computing
- **scipy** - Scientific computing

## Usage Examples

See the `examples/` directory for detailed examples of each feature.

## License

MIT License - See LICENSE file for details

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

For issues and questions, please open an issue on GitHub.
