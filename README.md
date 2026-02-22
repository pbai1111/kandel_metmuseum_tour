# Met Tour Audio Generator

## Setup

```bash
pip install requests
export ELEVENLABS_API_KEY="your-key-here"
```

To find your API key: elevenlabs.io → Profile → API Keys

## Generate Audio

```bash
cd met-tour
python generate_audio.py
```

This reads `audio_segments.json` and generates ~56 mp3 files into the `audio/` folder.

**Safe to re-run** — existing files are skipped. If a clip fails (rate limit, network), just run it again.

## Output

```
audio/
  stop01_museum_01.mp3
  stop01_kandel_01.mp3
  stop01_kandel_02.mp3
  stop01_kandel_03.mp3
  stop01_library_01.mp3
  stop01_library_02.mp3
  stop02_museum_01.mp3
  ...
```

## Cost Estimate

~56 clips, most 10-40 seconds of audio. Rough estimate: 8,000-12,000 characters total.
ElevenLabs pricing varies by plan, but this should be well under $1 on most paid plans.

## Tweaking

After hearing the first batch, you may want to adjust voice settings in `generate_audio.py`:

- **stability** (0-1): Lower = more expressive/variable, Higher = more consistent
- **similarity_boost** (0-1): Higher = closer to the original voice
- **style** (0-1): Higher = more stylistic expressiveness

The `library` voice (your clone) has higher similarity_boost to keep it sounding like you.

## Next Step

Once audio is generated, the HTML tour page will reference these files.
# kandel_metmuseum_tour
