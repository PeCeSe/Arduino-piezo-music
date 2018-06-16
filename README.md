# Piezo-music
Library for making piezo buzzer play songs with sheet music logic

## Getting Started

All you need to do is to make sure you have added this line somewhere near the top of your file:
```
#include "piezo-music.h"
``` 
Then, simply call this function in your run loop (or wherever you want it): 
```
playSong(BUZZER_PIN, your_melody, your_rythm, size, tempo);
```

Please note that both `your_melody` and `your_rythm` will be int arrays. `Tempo` is beats per minute.

## Example

So, let's say you want to play "Twinkle twinkle little star" (the hello world of music) and you find the sheet music:

![Twinkle Twinkle Little Star sheet music](https://image.ibb.co/dfffzd/twinkle_twinkle_sheet.png)

Let's first write all the notes in an array (see the available notes listed in `piezo-music.h`): 
```
int twinkle_twinkle_melody[] = {
  NOTE_C4, NOTE_C4, NOTE_G4, NOTE_G4, 
  NOTE_A4, NOTE_A4, NOTE_G4,
  NOTE_F4, NOTE_F4, NOTE_E4, NOTE_E4,
  NOTE_D4, NOTE_D4, NOTE_C4
};
```
Then write the rythm (where 4 is a quarter note, 2 is a half note etc.): 
```
int twinkle_twinkle_rythm[] = {
  4, 4, 4, 4, 
  4, 4, 2,
  4, 4, 4, 4, 
  4, 4, 2
};
```
Then simply call `playSong()`:
```
int size = sizeof(twinkle_twinkle_melody) / sizeof(int); // Get the length of your array/melody
playSong(BUZZER_PIN, twinkle_twinkle_melody, twinkle_twinkle_rythm, size, 40);
```

See `example-music.h` for more songs!

## Acknowledgments

This project is based on Arduino's [Play a Melody using the tone() function](https://www.arduino.cc/en/Tutorial/toneMelody) tutorial. I just wanted to add a couple of things like rythm, and put it in a handy little library. 
