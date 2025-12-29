# dc offset and the center spike

so you open your waterfall and see a big ugly spike sitting right in the middle, that is the dc offset

it happens because sdr hardware is not perfect, a small amount of energy leaks internally and shows up exactly at the frequency you are tuned to

it sits dead center because that point is zero hertz relative to your center frequency, it is not a real signal coming from the air, it is just internal noise from the sdr itself

this spike is annoying because if a real signal lands right there, the dc offset can cover it up completely, basically blinding you to that exact spot in the spectrum

the fix is simple, use offset tuning, instead of tuning directly to the signal you shift the center frequency slightly to the side

when you do that, the dc spike moves away from the signal, and you can view and process the part of the spectrum you actually care about without noise blocking your view.
