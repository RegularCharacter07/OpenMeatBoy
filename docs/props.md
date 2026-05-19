# `.props` Files

These files contain different variables for each of the playable characters.

## General Explanations

The file is in little endian.

This file contains three types of properties:
- Player Properties.
- Animation Properties.
- Effect Properties.

Player Properties contains the variables of the character's physics (such as speed, gravity, etc.).

Animation Properties contains the X and Y position variables for the character's animations (such as Idle, Walk, Run, etc.).

Effect Properties contains the X and Y position variables for character effects (such as splash, slide, etc.), it also has an S variable (probably speed).

There are two types of this file, some are complete and others are incomplete because they are missing information (the incomplete ones are found in unused characters like `dumbmeatboy.props`).

Complete files begin with `06 00 00 00` and incomplete files begin with `04 00 00 00`.

## Data (complete files)

- Beginning of file (always `06 00 00 00` if the file is complete).
- Run Speed (Player Property) `Float32`.
- Walk Speed (Player Property) `Float32`.
- Jump (Player Property) `Float32`.
- Wall Jump Up (Player Property) `Float32`.
- Wall Jump Out (Player Property) `Float32`.
- Wall Friction (Player Property) `Float32`.
- Drag (Player Property) `Float32`.
- Gravity (Player Property) `Float32`.
- Tile Bounds (Player Property) `Float32`.
- Kill Bounds (Player Property) `Float32`.
- Idle Offset X (Animation Property) `Float32`.
- Idle Offset Y (Animation Property) `Float32`.
- Idle2 Offset X (Animation Property) `Float32`.
- Idle2 Offset Y (Animation Property) `Float32`.
- Idle3 Offset X (Animation Property) `Float32`.
- Idle3 Offset Y (Animation Property) `Float32`.
- Walk Offset X (Animation Property) `Float32`.
- Walk Offset Y (Animation Property) `Float32`.
- Run Offset X (Animation Property) `Float32`.
- Run Offset Y (Animation Property) `Float32`.
- Run Fast Offset X (Animation Property) `Float32`.
- Run Fast Offset Y (Animation Property) `Float32`.
- Jump Offset Y (Animation Property) `Float32`.
- Jump Offset Y (Animation Property) `Float32`.
- Fall Start Offset X (Animation Property) `Float32`.
- Fall Start Offset Y (Animation Property) `Float32`.
- Fall Offset X (Animation Property) `Float32`.
- Fall Offset Y (Animation Property) `Float32`.
- Wall Slide Offset X (Animation Property) `Float32`.
- Wall Slide Offset Y (Animation Property) `Float32`.
- Turn Offset X (Animation Property) `Float32`.
- Turn Offset Y (Animation Property) `Float32`.
- Up Turn Offset X (Animation Property) `Float32`.
- Up Turn Offset Y (Animation Property) `Float32`.
- Down Turn Offset X (Animation Property) `Float32`.
- Down Turn Offset Y (Animation Property) `Float32`.
- Run Turn Offset X (Animation Property) `Float32`.
- Run Turn Offset Y (Animation Property) `Float32`.
- Death Offset X (Animation Property) `Float32`.
- Death Offset Y (Animation Property) `Float32`.
- Land Offset Offset X (Animation Property) `Float32`.
- Land Offset Offset Y (Animation Property) `Float32`.
- Appear Offset X (Animation Property) `Float32`.
- Appear Offset Y (Animation Property) `Float32`.
- End Level Offset X (Animation Property) `Float32`.
- End Level Offset Y (Animation Property) `Float32`.
- J. Airbrake Offset X (Animation Property) `Float32`.
- J. Airbrake Offset Y (Animation Property) `Float32`.
- F. Airbrake X (Animation Property) `Float32`.
- F. Airbrake Y (Animation Property) `Float32`.
- Up Slant Offset X (Animation Property) `Float32`.
- Up Slant Offset Y (Animation Property) `Float32`.
- Down Slant Offset X (Animation Property) `Float32`.
- Down Slant Offset Y (Animation Property) `Float32`.
- Ground Shock Offset X (Animation Property) `Float32`.
- Ground Shock Offset Y (Animation Property) `Float32`.
- Air Shock Offset X (Animation Property) `Float32`.
- Air Shock Offset Y (Animation Property) `Float32`.
- Land Offset X (Effect Property) `Float32`.
- Land Offset X (Effect Property) `Float32`.
- Land Offset S (Effect Property) `Float32`.
- Jump Offset X (Effect Property) `Float32`.
- Jump Offset Y (Effect Property) `Float32`.
- Jump Offset S (Effect Property) `Float32`.
- Wall Land Offset X (Effect Property) `Float32`.
- Wall Land Offset Y (Effect Property) `Float32`.
- Wall Land Offset S (Effect Property) `Float32`.
- Wall Jump Offset X (Effect Property) `Float32`.
- Wall Jump Offset Y (Effect Property) `Float32`.
- Wall Jump Offset S (Effect Property) `Float32`.
- Run Splash X (Effect Property) `Float32`.
- Run Splash Y (Effect Property) `Float32`.
- Run Splash S (Effect Property) `Float32`.
- Walk Splash X (Effect Property) `Float32`.
- Walk Splash Y (Effect Property) `Float32`.
- Walk Splash S (Effect Property) `Float32`.
- Run Fast Splash X (Effect Property) `Float32`.
- Run Fast Splash Y (Effect Property) `Float32`.
- Run Fast Splash S (Effect Property) `Float32`.
- Ground Splash X (Effect Property) `Float32`.
- Ground Splash Y (Effect Property) `Float32`.
- Ground Splash S (Effect Property) `Float32`.
- Wall Slide X (Effect Property) `Float32`.
- Wall Slide Y (Effect Property) `Float32`.
- Wall Slide S (Effect Property) `Float32`.
- Walk Delay (Effect Property) `Float32`.
- Run Delay (Effect Property) `Float32`.
- Run Fast Delay (Effect Property) `Float32`.
- Hill Damper (Player Property) `Float32`.
- Turn Friction (Player Property) `Float32`.
