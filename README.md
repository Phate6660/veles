# Veles
A song lyrics markup language, parser, and renderer. Name taken from the Slavic god.

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
