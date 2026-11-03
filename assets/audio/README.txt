CURRENT RUNTIME AUDIO (2026-11-04)
11 sounds, each with a 16-bit PCM WAV primary and MP3 fallback.
All runtime audio: music, ambience and SFX are 24 kHz mono (WAV and MP3).
WAV encoding: PCM signed 16-bit. Original duration, loop points and mixer gains retained.
MP3 is fetched only if WAV download/decode fails.
Original M4A and retired sound variants were archived outside the project before cleanup.
The notes below describe source provenance and historical processing, not current runtime file extensions.

--- Historical source and processing notes ---
Captain's Gold background music
Source supplied by user: 229409_1792427651_2.mp3 (1,338,207 bytes).
Runtime: captains-theme-loop.m4a (460,695 bytes), AAC 64 kb/s, 44.1 kHz stereo.
56-second loop with a baked 1.5-second crossfade between tail and head.
Original file in Downloads is unchanged.

Web Audio decodes once and loops with loopEnd=56 to exclude codec padding.
Starts after a user gesture. Music OFF stops the source and sets gain to zero.
Pauses while hidden and resumes at the saved position. Music gain is 0.1275 (15% below the previous 0.15). SFX have independent controls.
Music and SFX settings synchronize across same-origin tabs.

Coin flight: user 77fae3ab5b341cd.mp3 -> coin-flight.m4a, AAC mono 48 kb/s, 2866 bytes.
Chest impact: user universfield-coin-drop-229314.mp3 -> chest-impact.m4a, AAC mono 64 kb/s, 15101 bytes.
Both decode once after interaction, play through SFX gain; synthesized flight/impact removed.

Ocean ambience: user ab-f-031616-38732489-ocean-waves-ambience-01_yerWxidB.mp3.
Runtime ocean-loop.m4a: AAC stereo 64 kb/s, 32 kHz, 35725 bytes (source 213277).
First 5 seconds, baked 0.7-second tail/head crossfade; exact Web Audio loopEnd 4.3 seconds.
SFX bus only; gain 0.043218 normal / 0.14161 bonus, smooth 1.2-second target transition.
Decode once; stop on SFX OFF / hidden, preserve offset and resume; independent of Music setting.

Thunder: user fonoteca-raskat-groma.mp3 -> thunder-distant.m4a (33861 bytes). AAC mono 48 kb/s, 32 kHz. Distant treatment: 1800 Hz lowpass, gain 0.18, soft attack/tail. Plays once 0.8 seconds after lightning through SFX bus. Invalid source MP3 packets skipped during conversion; output decode verified.

Rolling loop: ported procedural roll noise from Sizzling Toons GameAudio (2-second cached noise, 18 Hz modulation, lowpass 1050 Hz). Pitch/filter/gain follow actual reel braking in base and bonus; stop fade 120 ms.
Original generated effects: treasure-win, collector-chime, treasure-suspense, suspense-tick. Reproducible physical-model generation in tools/generate-audio.cjs, mono AAC 64 kb/s. Replaced old oscillator melodies. Suspense fades out on anticipation cancellation.

Audio revision 2: win and anticipation replaced with short minor-key pirate reed/horn phrases and frame drums. Collector update now uses the user-supplied coin drop excerpt (first 0.55 sec), softened with 250-1800 Hz filtering, 0.65 gain and fades; no pitched electronic chime. Sample URLs versioned v2 to invalidate previous browser cache.
