<img src="ss1.png" width="800">

# WORDLE
i think we all know how wordle works still there will be a how to play below, also its minified with terser making it run on a data uri locally on your computer it does not need a server to host itself. 

## HOW TO PLAY
Guess the correct 5 letter word, you have 6 chances to guess it.
Certain colors means certain things regarding the guessed letter being in the word:
Green- it is in the word and in the correct spot.
Blue- it is in the word but not in the correct spot.

theres only one word for now, it reveals the answer after you use all the 6 attempts.

# NOTE
in the latter part, i added audio using webaudioapi, and it was a mess. the code made me learn alot about webaudio tho, and it was fun making the victory sound especially. typing every different letter has a slight variation which i gave by extracting the letter from "KeyA" or whatever the key is pressed down then taking the 3rd index sending it to the letter then the line letter.charCodeAt(0) turns a letter into a number, with A=65 up to Z=90, subtracting 65 gives 0 to 25, and adding that to 60(middle c) gives notes c4 up to c#6. each alphabet makes sound one semitone above the previous alphabet, which is a chromatic scale. for the victory music, i used the c major chord(C,E,G) added c6 at the end. i used midi note numbers to convert the notes to frequency where a4 is 69, the formula is f=440*2^((n-69)/12) which gives the frequency of particular note represented by a midi number. each note starts at its volumne vol and fades towards 0.001 over duration d, and the oscillator stops at the moment the fade ends, i set the exponentialrampToValue to 0.001 and not 0 because its exponential curve and they reach 0 at infinity also webaudio throws an range error if you write 0 inside it, 0.001 works well because its -60decibels which is basically no sound. after being done with all this the build.mjs was compressing it well above 3kb around 400 bytes over the limit, so i used a script made by Valerie, and its now around 2500 bytes.

## SCREENSHOT
<img src="ss.png" width="800">
<img src="ss2.png" width="800">