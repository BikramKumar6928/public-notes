# Add a subtitle file to video

```bash
ffmpeg -i input.mp4 -i input-subtitles.smi -c:v copy -c:a copy -c:s mov_text -metadata:s:s:0 language=eng output.mp4
```

# Deleting an added subtitle

```bash
ffmpeg -i input-with-subtitles.mp4 -c:v copy -c:a copy -map 0:v -map 0:a input-without-subtitles.mp4
```


# Extracting a subtitle file

```bash
ffmpeg -i input.mp4 -map 0:s:0 output.srt
```