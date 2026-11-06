# Locales

The texts are in `locales/<code>.json`. `en.json` and `sv.json` are included, and the language is picked with `Config.Locale` in `config/main.lua`.

## Adding a language

1. Copy `locales/en.json` to a new file, for example `locales/de.json`.
2. Translate the values. Keep the keys and the `{placeholders}` as they are.
3. Set `Config.Locale = 'de'`.

Keys you leave out fall back to English.

## Names that live in the locales

* Slot game names, taglines and bonus texts: `slots.<game>.*`
* Horse names for horse racing: `track.horses`, separated by `|`
* The casino name used for the blip: `common.casino`
