# MLB Statcast Data Dictionary (April–July 2024)

This file describes the features used in this project and expected value ranges/notes.
Source: MLB Statcast (via `pybaseball.statcast`). Units and ranges are approximate; treat them as sanity guides rather than hard rules.

## Player Information
- **batter** (int): MLBAM player ID of the batter.
- **pitcher** (int): MLBAM player ID of the pitcher.
- **stand** (category: `L`/`R`): Batter stance (left or right).
- **p_throws** (category: `L`/`R`): Pitcher throwing hand.

## Strike Zone (personalized per batter)
- **sz_top** (float, feet ~2.5–4.5): Top of the batter’s strike zone. Should be > `sz_bot`.
- **sz_bot** (float, feet ~1.0–2.1): Bottom of the batter’s strike zone.

## Pitch Context
- **balls** (int, 0–3): Balls in the count **before** the pitch.
- **strikes** (int, 0–2): Strikes in the count **before** the pitch.
- **inning** (int, ≥1): Inning number.

## Pitch Release & Movement
- **release_speed** (float, mph ~35–105): Pitch velocity at release.
- **release_pos_x** (float, feet ~−3.5–3.5): Horizontal release point.
- **release_pos_z** (float, feet ~3.0–8.0): Height of the ball at release.
- **pfx_x** (float, feet ~−1.5–1.5): Horizontal movement (movement relative to a spinless trajectory).
- **pfx_z** (float, feet ~−2.5–2.5): Vertical movement (positive indicates “rise” relative to gravity-only path).
- **release_extension** (float, feet ~4.5–7.5): Distance in front of rubber where ball is released.
- **arm_angle** (float, unitless/derived): Approximate delivery arm angle.

## Plate Crossing Location
- **plate_x** (float, feet ~−2.0–2.0): Horizontal location as the pitch crosses the front of home plate. 0 = center. Strike-zone half-width ≈ 0.83 ft.
- **plate_z** (float, feet ~0.0–7.0): Vertical location at the plate. 

## Pitch Result
- **description** Text label of the pitch outcome (e.g., `ball`, `called_strike`, `swinging_strike`, `foul`, `hit_into_play`, etc.).
