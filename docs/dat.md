# `.dat` Files (What we know so far)
In Super Meat Boy, `.dat` files are used to store game data, like sounds, animations, and textures. Most notably, there are three different types of `.dat` files: Game data, audio data, and save data.

## Game data & Modern audio data
For game data and modern audio data `.dat` files, the header starts off like this:
- Total number of directories (Int32)
- Directory info (Instanced for every directory):
    - Directory index (Int32)
    - Unknown, should be at least 33 to avoid issues (Int32)
- Total number of files (Int32)
- File info (Instanced for every file):
    - Offset (Int32)
    - Size (Int32)
    - Directory index (Int32)
- Size of directory names payload (Int32)
- Size of file names payload (Int32)
- Payload of directory names separated by null terminators at the end of each name
- Payload of file names separated by null terminators at the end of each name

Following the header begins the payload of all file data.

## Audio data (ogversion)
For audio data `.dat` files (the ogversion branch specifically), The header starts like this:
- Strange 20 byte data stored as 5 Int32's (Could be signature)
    - `02 00 00 00` `00 00 00 00` `00 00 00 00` `01 00 00 00` `35 00 00 00`
- Number of files (Int32)
- Sound info (Instanced for every sound, 12 bytes per instance):
    - Offset (Int32)
    - Size (Int32)
    - Unknown, should be zero (Int32)
- Unknown 8 byte data:
    - `10 00 00 00` `B7 3A 00 00`
- First two names of folders in the file, with null terminator at end of each name (`audio`, `audio/sfx`)
- Names of files separated by null terminators at the end of each name

Following the header begins the payload of audio data.