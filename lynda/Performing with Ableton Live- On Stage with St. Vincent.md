# Performing with Ableton Live: On Stage with St. Vincent

## Software Overview

1. Ableton Live
2. [Reason](https://www.propellerheads.se/en/reason) for software instruments
	* Contains huge rack of software instruments
	* Reason is great for some sounds although Ableton sound design capabilities are used just as much, if not more
3. Several plugins
	* [Diva](https://www.u-he.com/cms/diva): Recent favorite that is a virtual analog synthesizer
	* [Stringmachine](https://www.gforcesoftware.com/products/vsm): Great emulator for strings
	* [Arturia Mini V](https://www.arturia.com/products/analog-classics/mini-v/overview): moog emulator that is used quite a bit

## Ableton Live set layout

### Keeping the band and computer on the same page
* Two click tracks
* Recorded count off before each song starts
* Track for starting pitch reference in case the vocalist needs to come in before the music starts

### Instruments

* Separate tracks for each midi controller and drum trigger setup


### Program Change

Separate tracks just for program change messages that Mintseris uses to change the patches on the other musicians instruments from his keyboard (this is so they don't have to think about that stuff while they're interacting with the audience)


## Preparing to use a click

Sometimes you may not have a choice of using a click track during the show if there is any element in the music that requires the computer to be in sync with the band. Some examples include:

  * time defects
  * arpeggiators
  * most kinds of pre recorded audio if you're using it
  * patch change automation.

Ableton live has a metronome button in the toolbar, however having a dedicated click track offers more control. For example you can:

  * automate the volume of the click
  * more routing options (easily change the tonal character of the click or even create simple beat patterns to make the click a little more musical

Performers need to wear headphones or in-ear monitors

## Creating click tracks

Use a midi note to trigger the click.wav via a Simpler module. One this is done you can save. Drag the clip over to the browser, saving it as a template. From there you can drag and drop this template onto a MIDI track to create a click track. This lets you add them to other songs with different tempos. This is preferred since Live won't have to warp the audio, causing unecessary cpu processing.

I can also automate the click volume, so that it is louder during the chorus but soft during the verse.

## Count-off and starting pitch

Count-off

Record yourself counting 1,2,3,4 and bounce them into four individual tracks. From there create a `COUNT` track and drag in Impulse onto a MIDI track.
	* Impulse is designed for drum programming, but for ourpurposes it's just a sampler with eight sample slots.

	
### Starting Pitch

Unless the singer has perfect pitch, there has to be some frame of reference if they're starting a song with just vocals

1. Drag the `Operator` instrument onto a track (which will automatically create a MIDI track).


# Keyboard Presets

## Creating a song preset is an Instrument Rack

1. Create a new MIDI track (cmd + shift + t)
2. Specify controller input via the `MIDI From` dropdown menu on the track and select the midi channel below that
3. Turn on monitoring
4. Name the track (cmd + r)