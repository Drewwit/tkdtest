# White Belt Orientation Tour - Prime Martial Arts

Two self-contained versions of the onboarding tour, built from the July 1 drone/iPhone shoot. Both use the official White Belt Orientation quiz (all 10 questions) and the Prime blue/black palette.

## Files

- `tour.html` - **Version A: "Belt Path"** - scrolling guided tour. 7 stops, each with an auto-looping drone clip and its orientation question(s). Progress bar + belt spine fill as questions are answered; full drone flyover video at the bottom.
- `explore.html` - **Version B: "Explore the School"** - fullscreen photo walkthrough. 4 scenes (Entrance → Lobby → Hallway → Training Floor) with pulsing hotspot pins. Question pins open a panel with the drone loop + questions; small "i" pins are bonus info (awards wall, seating, check-in tablet). Score chip tracks 10/10.
- `clips/` - web-optimized media (H.264, muted). Stop loops are 7–11s, 170–500 KB each. `full_flyover.mp4` is the whole 2:04 flythrough (8 MB). `scene*.jpg` are the fullscreen backdrops.

Open either HTML file directly in a browser to test - no server needed, everything is relative paths.

## Putting it on Squarespace

Squarespace code blocks can't host the video files themselves. Two options:

1. **Squarespace file storage**: upload each clip via any Link editor (Link → File → Upload), which stores it at `/s/filename.mp4`. Then in the HTML change `clips/stop1_entrance.mp4` → `/s/stop1_entrance.mp4` (same for scenes/flyover), and paste the HTML into a Code Block or as a full page injection.
2. **External host (recommended for the flyover)**: keep the loops on Squarespace storage, put `full_flyover.mp4` on YouTube (unlisted) and swap the `<video>` for an embed - saves bandwidth.

The quiz answers match the Google Form, so this can either replace the form or be the "study guide" students do before submitting it.

## Source footage used

- `dji_..._150258_15` (your pick) - stops 1, 7, full flyover
- `dji_..._151634_0015` (4K) - stops 2, 3
- `dji_..._151358_0014` (4K) - stops 4, 5, 6
- `IMG_7778 / 7781 / 7780 / 7784` - the four fullscreen scenes in Version B
