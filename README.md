# Make a karaoke track from a YouTube song

Search YouTube, download the audio with yt-dlp, separate vocals with Demucs (`mdx_extra`, two stems), transcribe with faster-whisper, and play the instrumental in the React page. If `GENIUS_ACCESS_TOKEN` is set, lyrics can be corrected with Genius. The token is optional.

`setup.sh` copies `env.example`, and that file is not in the repo, so use the steps below.

## Start the player

You need Python 3, Node.js, and ffmpeg.

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
cd frontend && npm install && cd ..
```

`requirements.txt` includes FastAPI, yt-dlp, faster-whisper, lyricsgenius, and demucs.

```bash
# optional
export GENIUS_ACCESS_TOKEN=your_token
cd backend && python main.py
```

The API listens on port 8000. In another terminal, from `frontend`, run `npm start` and open http://localhost:3000.

## License

[MIT](LICENSE)
