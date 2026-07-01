# audio-to-video

Convert audio files (MP3) and cover images (JPG/PNG) into YouTube-ready MP4 videos with an audio frequency visualizer bar.

## Usage

Trigger the workflow via GitHub Actions UI or API:

```bash
curl -X POST \
  -H "Authorization: Bearer <YOUR_TOKEN>" \
  -H "Accept: application/vnd.github+json" \
  https://api.github.com/repos/pilgrimdelamare/audio-to-video/actions/workflows/render.yml/dispatches \
  -d '{
    "ref": "main",
    "inputs": {
      "audio_url": "https://example.com/audio.mp3",
      "cover_url": "https://example.com/cover.jpg",
      "song_id": "my-song-001"
    }
  }'
```

The rendered MP4 will be available as a workflow artifact for 24 hours.

## Output

- Resolution: 1920×1080
- Video: H.264, CRF 22
- Audio: AAC 192kbps
- Visualizer: frequency bars (880px from bottom)
