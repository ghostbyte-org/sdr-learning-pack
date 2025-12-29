# iq files and formats

iq files are basically just recordings of the radio spectrum, think of them like a voice memo, but instead of recording sound, they record radio signals, it is just a long list of iq sample snapshots saved to disk

you will usually see two main types, wav files and raw iq files, wav files are easier to work with because they include a header that tells the software things like the sample rate

raw iq files are different, they are just the naked data with no instructions at all, the software has no idea how fast they were recorded unless you tell it

this means when you load a raw file, you must manually set the exact sample rate it was captured at, if you get this wrong the signal will look shifted, audio will sound like demons or chipmunks, and demodulation will completely fail

so if you open an iq file and it looks dead or broken, the file usually isn’t bad, you are just playing it at the wrong speed

files are not magic, they are just recorded streams, playback has to match capture exactly for things to make sense
``
