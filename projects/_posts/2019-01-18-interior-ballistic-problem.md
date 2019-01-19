---
title: Interior Ballistic Problem
updated: 2019-01-18
---

## Jack’s Antique Software 

Last night a good friend of mine, Jack, came to talk to me about calculating the wild math that goes on inside an artillery piece when it is being fired.

Jack’s thesis is about a new artillery piece he is designing, and his supervisor has offered to let him run his tests on the software that he uses to check his own numbers.

His supervisor has been faithfully using the exact same set of punch cards since the 1950s, which were all written based on some papers written before or during the second world war. The machine that can run this program is protected behind some top secret walls, and takes forever to do some fairly simple calculations. 

Jack managed to get some samples of the input and output, some example files of the program working correctly, and a few lines of code that had been printed out. 

## Documentation

The first document we have access to is one describing every *record* that the program requires. This is a pretty brutal way to do input, but given that these records have been collected into cute little `.in` files we have decided that we would like to use. 

The program produces `.out` files too, and we have some examples that have been verified. They are very verbose text output that is actually more helpful than the actual documentation, every variable is pre-pended with a string describing exactly what it is.

Next are the two papers that contain all of the math that we need to do to re-create the program.

While there are some obvious ways this program could be improved, we will attempt to faithfully re-create the program functionality exactly. The hope is that this program will be familiar enough for the professor to use himself. For this reason the fairly useless and verbose `.in` and `.out` file formats will be kept as close as original as possible. We will probably also output the majority of the variables into a `.csv` for use elsewhere.

## Programming Time

### Parsing Input

The first thing I did was create a simple python function that reads in the `.in` file and fills in tons of very long-winded variable names. All of these variables are stored for later use. The program faithfully prints out every variable it reads in, sometimes in a strange tabbed-out manner. Other than a few spelling mistakes I faithfully re-created the exact same formatting in my `.out` file. 

### Quick Math

#### Area of the bore

The first math problem was calculating a variable called `area of the bore m^2`, this number was a float, and the only useful inputs to calculate this are the `groove diam in m`, `land diameter in m`, and `groove/land ratio`. Luckily calculating two circles, multiplying them by the ratio, managed to produce the exact same output as the printout from the stone age. My first success, and I didn’t even need to consult the paperwork.

