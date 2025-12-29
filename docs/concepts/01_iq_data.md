# iq data – the core of sdr

in sdr almost everything starts with iq data

instead of dealing with the rf signal directly, the radio converts it into two parts, i and q

i (in-phase) and q (quadrature) together describe the signal as a point on a complex plane, which means we don’t just keep how strong the signal is, but also how it is changing over time

this matters because most real modulations like fm, fsk, qam, etc depend on phase and frequency changes, not just amplitude, if you only keep a single waveform you lose half the information

in practice an sdr samples the signal and outputs a stream of complex values (i + jq), where each sample represents the signal at a specific moment in time

when you don’t have sdr hardware, the same iq data can be stored in files like wav or raw binaries and fed into gnu radio, so you can still learn, analyze signals, and build flowgraphs without transmitting or receiving anything live

if you don’t understand iq data properly, filtering, demodulation, or even replay attacks won’t really make sense later
