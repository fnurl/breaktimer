# README

A break timer contained in a single html file.

Allow sounds for an alarm when done:

- Firefox: When timer is done, there will be a crossed over play icon in the
  location bar. Click on this and allow audio. The next time, the timer will
  beep. See https://support.mozilla.org/en-US/kb/block-autoplay
- Chrome: Click on the 'i' icon in the location bar, then "Site settings".
  Change "Sound" to "Allow".
- Safari: Right-click in location bar, then select "Settings for This
  Website..." and set "Auto-Play" to "Allow All Auto-Play"


## Behaviour / API

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

- **5 minute break, use default language**: `breaktimer.html?m=5`
- **15 minute break, use Swedish language**: `breaktimer.html?lang=sv&m=15`


### Limitations

Font size is set with breaks < 100 minutes in mind.


## Development notes


### base64 encoding of image and sound

(use GNU base64)

`$ base64 --wrap=76 srcfile > trgfile`


### resize image (using imagemagick)

`$ magick convert src.png -resize '16x16' out.png`


### Sound and image sources

Sound: "Alarm digital clock beep" from https://mixkit.co/free-sound-effects/beep/
Favicon: https://www.pngrepo.com/svg/23258/timer