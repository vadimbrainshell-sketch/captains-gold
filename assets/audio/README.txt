Captain's Gold background music
Source supplied by user: 229409_1792427651_2.mp3 (1,338,207 bytes).
Runtime: captains-theme.m4a (474,724 bytes), AAC-LC 64 kb/s,
44.1 kHz stereo, 57.709 seconds. About 64.5% smaller.
Original file in Downloads is unchanged.

FFmpeg conversion:
ffmpeg -i INPUT.mp3 -map 0:a:0 -vn -map_metadata -1 -c:a aac
  -b:a 64k -ar 44100 -ac 2 -movflags +faststart captains-theme.m4a

HTML audio with loop enabled and preload=none. Starts after a user gesture
when Music is enabled; pauses while hidden/off and resumes at the same time.
Volume is 0.30. Sound effects remain independently controlled.
