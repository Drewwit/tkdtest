# White Belt Orientation Tour - Prime Martial Arts

Two self-contained versions of the onboarding tour, built from the July 1 drone/iPhone shoot. Both use the official White Belt Orientation quiz (all 10 questions) and the Prime blue/black palette.

## Files

- `tour.html` - **Version A: "Belt Path"** - scrolling guided tour. 7 stops, each with an auto-looping drone clip and its orientation question(s). Progress bar + belt spine fill as questions are answered; full drone flyover video at the bottom.
- `explore.html` - **Version B: "Explore the School"** - fullscreen photo walkthrough. 4 scenes (Entrance → Lobby → Hallway → Training Floor) with pulsing hotspot pins. Question pins open a panel with the drone loop + questions; small "i" pins are bonus info (awards wall, seating, check-in tablet). Score chip tracks 10/10.
- `clips/` - web-optimized media (H.264, muted). Stop loops are 7–11s, 170–500 KB each. `full_flyover.mp4` is the whole 2:04 flythrough (8 MB). `scene*.jpg` are the fullscreen backdrops.

Open either HTML file directly in a browser to test - no server needed, everything is relative paths.

## Mobile versions

Each prototype has a phone-first build: `tour-m.html` (full-screen card per stop, swipe between stops), `explore-m.html` (swipe between rooms, bottom-sheet questions), and `flight-m.html` (cinematic media band, bottom-sheet questions, swipe left to take off). All buttons sit in the thumb zone and tap targets are 44px+.

Routing is automatic: phones and portrait tablets get the `-m` pages, desktops and landscape iPads stay on the desktop pages. Escape hatches for testing: add `?desktop=1` to any desktop page to stop it routing away, or `?mobile=1` to view an `-m` page in a desktop browser.

## Putting it on Squarespace

Squarespace code blocks can't host the video files themselves. Two options:

1. **Squarespace file storage**: upload each clip via any Link editor (Link → File → Upload), which stores it at `/s/filename.mp4`. Then in the HTML change `clips/stop1_entrance.mp4` → `/s/stop1_entrance.mp4` (same for scenes/flyover), and paste the HTML into a Code Block or as a full page injection.
2. **External host (recommended for the flyover)**: keep the loops on Squarespace storage, put `full_flyover.mp4` on YouTube (unlisted) and swap the `<video>` for an embed - saves bandwidth.

The quiz answers match the Google Form, so this can either replace the form or be the "study guide" students do before submitting it.

## Version C: "The Flight" (flight.html)

Eight flight legs cut from the continuous `dji_..._150258_15` flythrough. Each leg's video ends on the exact frame used as the landing still, so the crossfade from flying to exploring is seamless. POIs sit on the stills; answering unlocks the next takeoff.

**Adding the exterior shots**: add new legs to the START of the `LEGS` array in flight.html (approach, parking lot, front door). Each leg needs a `video` (mp4, 1280w, muted), a `still` (the last frame: `ffmpeg -sseof -0.1 -i leg.mp4 -frames:v 1 still.jpg`), and optional `pois`. The flight path, progress, and preloading adapt automatically.

## Source footage used

- `dji_..._150258_15` (your pick) - stops 1, 7, full flyover
- `dji_..._151634_0015` (4K) - stops 2, 3
- `dji_..._151358_0014` (4K) - stops 4, 5, 6
- `IMG_7778 / 7781 / 7780 / 7784` - the four fullscreen scenes in Version B
