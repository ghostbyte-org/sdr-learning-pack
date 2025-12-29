# fm receiver using an iq file

## goal

we are going to turn raw math into music. the goal of this lab is to take a recorded chunk of radio spectrum (an iq file) and build a working fm receiver from it.

this proves you understand sample rate, filtering, and how radio actually works, all without needing sdr hardware yet.

---

## what you need

- gnu radio companion installed  
- a sample iq file containing an fm broadcast station (often named something like fm_capture.iq, usually recorded at 2msps)  
- headphones or speakers  

---

## flowgraph overview

think of this like a pipeline. data comes in, gets cleaned, reshaped, and finally turned into sound.


file source => throttle => low pass filter => wbfm receive => audio sink

each block does one job, and breaking one part breaks the whole chain.

---

## steps

### 1. file source
point this to your `.iq` file and set output type to `complex`.

### 2. variables
create a variable called `samp_rate` and set it to match the recording exactly (usually `2e6`).

### 3. throttle
connect a throttle block after the file source so the file plays at real-time speed.

### 4. low pass filter
use this to clean up the signal before demodulation.

- decimation: `4`  
- cutoff freq: `100e3`  
- transition width: `1e6`  

### 5. wbfm receive
this block converts fm radio into audio.

- quadrature rate: `500e3`  
- audio decimation: `10`  

### 6. audio sink
set sample rate to `48000` and connect it.

### 7. run it
hit play and listen.

---

## common mistakes

- chipmunk or demon audio → sample rates do not match  
- static or noise → filter missing or cutoff too wide  
- system freeze → throttle block missing  
- silence → wrong file path or muted audio  

---

## what you should observe

if it works, you will hear clear fm audio. you just built a radio receiver entirely in software.
