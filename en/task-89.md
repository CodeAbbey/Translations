This task is the reverse of [Pitch and Notes](./pitch-and-notes) (so perhaps you may want to read or solve it first) -
suppose you are building the electronic tuner for
guitar, violin or piano - and you already connected microphone to microcontroller and succeeded in registering the
sound wave, smoothering it and measuring its frequency.

Now the only thing remained is to write a part of program responsible for determining the note played by its frequency.  
I.e. if the device have detected sound of `440 Hz` it should be able to tell that note `A4` is played.

Since in reality instruments could be slightly out of tune, you need not expect that pitch will be mathematically exact.
Nevertheless you'll be able to determine the nearest note. I.e. frequencies of `433 Hz` or `449 Hz` should anyway be
classified as `A4`.

**Input data** contains number of notes to identify.  
The next line will provide the frequencies, separated by spaces.  
**Answer** should contain identified note names.

Example:

    input data:
	16
    185.4 115.3 203.9 55.2 52.7 86.6 932.3 229.8 61.8 66.1 363.7 771.4 594.4 48.2 102.6 222.4
	
	answer:
	F#3 A#2 G#3 A1 G#1 F2 A#5 A#3 B1 C2 F#4 G5 D5 G1 G#2 A3
