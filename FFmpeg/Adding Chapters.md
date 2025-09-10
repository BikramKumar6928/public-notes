# Adding Chapters to videos

Create chapters in this format

```
;FFMETADATA1

[CHAPTER]
TIMEBASE=1/1000
START=0
#chapter ends at 0:01:18
END=78000
title=Progeny
[CHAPTER]
TIMEBASE=1/1000
START=78000
#chapter ends at 0:04:59
END=299000
title=Tailo Village
[CHAPTER]
TIMEBASE=1/1000
START=299000
#chapter ends at 0:07:05
END=425000
title=Elo & Lana
```

Use this command to add chapters

```bash
ffmpeg -i input.opus -i chapters-ff.txt -map_metadata 1  -c:a copy output_with_chapters.opus
```

This will lead to loss of cover image.

A workaround can be to extract the image earlier and re embed the cover in the resultant file.