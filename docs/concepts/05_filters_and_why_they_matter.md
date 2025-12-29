# filters and why they matter

think of filters as the bouncer for your radio, they stand at the door and decide which frequencies get in and which ones stay out

without filtering, your sdr is trying to listen to everything at once, which is just chaos, filters cut out the frequencies you do not care about so the signal you want can stand out clearly

a low-pass filter lets the low frequencies through and blocks the high ones, while a band-pass filter isolates a specific slice in the middle, like focusing a flashlight on one spot in a dark room instead of lighting up everything

this matters because if you send a bunch of random noise into your demodulator, it will try to turn that static into data and fail

proper filtering cleans things up before demodulation, lowers the noise floor around your signal, and makes gain actually useful instead of just making everything louder.
