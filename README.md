# README

A break timer contained in a single html file. Use it e.g. during online
meetings to inform participants of how much break time is left. Live version
here: https://fnurl.github.io/breaktimer/


## How to use

Either use the live version at https://fnurl.github.io/breaktimer/ or save the
[html-file](https://raw.githubusercontent.com/fnurl/breaktimer/main/break.html)
to your computer and open it in your web browser when needed.

**Tip**: Open the page with a configured break time and bookmark it for easy
access.

See [configuration](#configuration) below for details on setting number of
minutes and language.


## Beeps when done

**Allow sounds** in your browser if you want some small beeps when done:

- **Firefox**: When timer is done, there will be a crossed over play icon in the
  location bar. Click on the icon and choose *"Allow Audio and Video"* in the
  *Auto Play* permissions drop-down. The next time, the timer will beep. More
  information: https://support.mozilla.org/en-US/kb/block-autoplay
- **Chrome**: Click on the 'i' icon in the location bar, then *"Site settings"*.
  Change *"Sound"* to *"Allow"*.
- **Safari**: Right-click in location bar, then select *"Settings for This
  Website..."* and set *"Auto-Play"* to *"Allow All Auto-Play"*


## Configuration

The following parameters can be passed to the page:

- `m=<minutes>`: Provide the number of minutes the break should last. Defaults
  to `10`.
- `lang=<language>`: Current options are `en` and `sv`. Defaults to the
  browser's preferred language (fallback=en).
- `debug`: If the debug parameter is given (no value), the timer runs 10x
  faster.

Add a `?` after the name of the file followed by a parameter. Separate multiple
parameters with a `&`.


### Examples

The order of the parameters does not matter.

- **5 minute break, use default language**: [`breaktimer.html?m=5`](https://fnurl.github.io/breaktimer/?m=5)
- **15 minute break, use Swedish language**: [`breaktimer.html?lang=sv&m=15`](https://fnurl.github.io/breaktimer/?lang=sv&m=15)
- **Default 10 minute break, use English language**: [`breaktimer.html?lang=en`](https://fnurl.github.io/breaktimer/?lang=en)


### Limitations

Font size of timer is set with breaks shorter than 100 minutes in mind.


## Development notes


### Adding more languages

Translations are stored in a plain JS object around line 437 in the html file.
If you want to add an additional language, just copy the pattern and add a new
language section.


### base64 encoding of image and sound

(use GNU base64)

`$ base64 --wrap=76 srcfile > trgfile`


### resize image (using imagemagick)

`$ magick convert src.png -resize '16x16' out.png`


### Sound and image sources

- Sound: "Alarm digital clock beep" from https://mixkit.co/free-sound-effects/beep/
- Favicon: https://www.pngrepo.com/svg/23258/timer