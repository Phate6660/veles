# Veles
A song lyrics markup language, parser, and renderer. Name taken from the Slavic god.

## Running
`$ luajit veles /path/to/lyrics/artist - album - title.txt`

Example:
```
$ luajit veles examples/Nothingface\ -\ An\ Audio\ Guide\ to\ Everyday\ Atrocity\ -\ The\ Sick.txt
Reading lyrics from examples/Nothingface - An Audio Guide to Everyday Atrocity - The Sick.txt:
Found line of lyrics: Scratch the tears in for good...
Found line of lyrics: Sadist...
Found line of lyrics: Feels good...
Found line of lyrics: Life can't hurt on tv...
Found line of lyrics: Godspeed...
Found line of lyrics: Lucky now...
Found line of lyrics: When he grabs your hand, do you lick again?
Found line of lyrics: But the taste has changed, flesh remains.
Found a section declaration: [Chorus]
Section name: Chorus
Found line of lyrics: See what you go through...
Found line of lyrics: With bleeding eyes...
Found line of lyrics: Got what you came for...
Found line of lyrics: When hate is blind...
Found an end section declaration
Found a section declaration: [Refrain x4]
Section name: Refrain
Found a repeat amount: 4
Found line of lyrics: You told me not to lie!
Found an end section declaration
Found line of lyrics: Anger persists to drown...
Found line of lyrics: Love it...
Found line of lyrics: Loathes you...
Found line of lyrics: Say your knife just won't kill...
Found line of lyrics: Try hard...
Found line of lyrics: Want it now...
Found line of lyrics: When the taste has changed, do you rest your face?
Found line of lyrics: No eyes will close, the hole grows.
Found a variable: <Chorus>
Found a variable: <Refrain x8>
Found a repeat amount: 8
Found a comment: --Instrumental Section--
Found a variable: <Refrain x8>
Found a repeat amount: 8
Found a section declaration: [Coda x9]
Section name: Coda
Found a repeat amount: 9
Found line of lyrics: The start of new days...
Found line of lyrics: Has nothing changed...
Found line of lyrics: The sick knows no pain...
Found an end section declaration
```

## Design
- Sections can be denoted with `[]`, for example `[Refrain]`.
- Sections can be accessed via a variable, for example `<Refrain>`.
- Repeated amounts can be placed inside a `[]` or `<>`, for example `[Refrain x4]`.
  + Repeated amounts do not carry over, they are a one time thing. So you can do:
    * `[Refrain x4]`
    * `<Refrain x8>`
- Comments can be placed with `--Comment--`.
- Timestamps can be put in place for sections or individual lines with the format `#-HH:MM:SS-#`.
- Sync with the music player (or parse the song?) to find incorrect timestamps for the songs.
- Verses don't need any section declaration since they usually aren't repeated.
- Check for missing grammar and punctuation in the lyrics.

## TODO
- Parse the lyrics [WIP]
- Expand the parsed lyrics [TODO]
- Render the lyrics [TODO]
