# `.am` Files

These are used to store animation information that is exported from Flash. Sadly, this is a flawed format with many versions; each is practically the same with only small differences, so I will describe the two that the newest build uses.

# Basic

I need to clarify some things before I can describe.

When I'm referencing booleans in the file it is a `uint32`: when it's 1 it's `TRUE`; if 0 then `FALSE`.

## Data formats 

- Dataframe:
    > It's used absolutely everywhere; you can interpret this as the changes that happen in the keyframe.

    > It can be a Symbol Reference or a Texture Reference (It technically can be a _ftex reference too but it is used very sparingly — explanation below).
    

## General Explanations

Read this a second time after you read the structure of the file if you don't understand something.

> This file is in a stack format. What I mean by that: the file indexes for dataframes and the usage of the footer values on the right texture are done from top to bottom like in the symbol name list. So first are symbols, then ftex, and lastly textures.

> The two types are different from each other: one includes ftex and audio (`Signed Files`) and the ones that don't are `Unsigned Files`.

> The game handles text simply: every text that has localization is called ftex (Flash text). In the am files they are always at the very bottom of the Symbol Name Table.

> Also, the game never uses ftex as-is: it uses a wrapper symbol with the `_t` postfix. Using ftex in a symbol with another symbol may lead to a crash.

> The layering is also based on the order of the timelines, like in Flash.

> The keyframes use a second-duration timer. For the seconds specified it shows up or does the tween in that time.

> On one timeline there can't be two active keyframes.

# Header

There are two types of headers that separate the two types of am files.

## - Signed

- A Signature `F101` or `001F`
- Symbol Name Table size in `uint16`
- Symbol Count `uint16`
- Frame Rate (Usually just 30 `float`)
- Ftex Count `uint32`

Then it's a Name Table for all the symbols in the file (null terminated):

- Symbol Names `String`
- Ftex Definitions `String`

## - Unsigned

- Symbol Name Table size in `uint16`
- Symbol Count `uint16`
- Frame Rate (Usually just 30 `float`)

Then it's a Name Table for all the symbols in the file (null terminated):

- Symbol Names `String`
# Data 

For the actual data it's easy: it's all stacked on top of each other.

- Movie Clip:
    - Packed data:
        - Looping
            - & the Packed value
        - Number of layers
            - Bit shift the Packed value to the Right (>>)
    - Useless Data `12 bits`
    - Vector Of Timelines:
        - Just Keyframe Count `uint32` — nothing else

    - Vector Of Keyframes:
        - Is a Tween `bool`
        - Dataframe Count `uint32`
        - Number Of Seconds The KeyFrame Will Be active `float`

        If Signature:
        - An `int32`
            > with the index of the audio clip; if it's -1 it doesn't have audio
        - Two `floats`
            > I have no idea what they do; they are set but don't change anything, so probably useless

        - Vector Of DataFrames:
            - Index `uint32`
            - X `float`
            - X `float`
            - X `float`
            - X Scale `float`
            - Y Scale `float`
            - X Skew `float` (Used For Rotation)
            - Y Skew `float` (Used For Rotation)
            - X Offset `float` (Move the dataframe only 0.018 that amount)
            - Y Offset `float` (Move the dataframe only 0.018 that amount)
            - 8 `uint16` for RGBA:
                > For context, it uses two `uint16` for color: one for the base color and the second for addition. Even alpha has addition but it doesn't do anything. If you want a black data frame, set everything to 0 except for the base alpha; if you want a completely white object, use 255 for all.

# FOOTER
The hardest part to decode.

- Vector of Index, x-size, y-size values `floats`
    > The indexes are incremented by 2 for some reason and they don't represent the texture the values are for; they are still in a stack.

    > Used for textures only; for symbols it's 0,0. So mostly the first part of the vector will be 0,0 because of the stack format of the file.

- If Signature:
    - Audio Count `uint32`
    - Name List of Audio Files (null terminated strings)

