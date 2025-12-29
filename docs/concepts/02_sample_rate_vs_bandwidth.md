# sample rate vs bandwidth

sample rate and bandwidth are related, but they are not the same thing, and mixing them up is one of the most common mistakes in sdr

bandwidth is how wide your view is, it tells you how big of a slice of the radio spectrum you can see at one time, think of it like the width of a highway, more bandwidth means more lanes and more cars visible at once

sample rate is how fast your hardware is taking snapshots of that highway, it is the speed of your camera, if you want to see cars moving really fast on a wide highway you need a camera that clicks fast enough, otherwise everything turns into a blur or you miss cars completely

this is where people get it wrong, increasing sample rate does not create new signals or magically make a signal wider, it only decides how much frequency space you are able to capture around the center frequency

here is the catch, you cannot actually use large bandwidth if your sample rate is trash, sample rate is the hard limit, if you try to open a 20mhz window but you only sample at 2mhz you are going to lose information and get garbage data

this is why you can have a very high sample rate and still see a narrow signal, or a wide signal that gets cut off if the sample rate is too low

when the signal bandwidth is larger than what the sample rate can support, aliasing happens, which breaks demodulation, ruins captures, and makes replay experiments fail later

so in simple terms, bandwidth is how wide the road is, sample rate is how fast you are looking at it, and sample rate decides how much of that road you can actually use. 
