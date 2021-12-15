# Four the Win!
Four the Win! is a versatile Connect Four program capable of solving different variants.

## Background
The original Connect Four game was independently solved in 1988 by James Allen then Victor Allis. The player who starts is guaranteed to win in less than twenty-one moves. The winning strategy is adequately documented and can help improve any player's skill in the game.

Hasbro introduced four new variants to Connect Four in 2009: PopOut, Pop 10, Power Up, and Five-in-a-Row. Jukka Pekkala solved PopOut in 2014 with comprehensive computer analysis in his master's thesis. He states PopOut offers a significant advantage to the first player allowing it to win sooner. The remaining three remains unsolved, but I did solved Five-in-a-Row to a draw by modifying John Tromp's Fhourstones program.

My program and my Connect Four skills confirmed his analysis, and with perfect play, the first player will win in at most eleven moves. Most code is original, but the algorithms used are not since they are profoundly relevant for a game solver. The only unoriginal code deals with 128-bit integers for boards too large to fit in 64 bits, which are taken from this repository: https://github.com/calccrypto/uint128_t

## Features
Four the Win! can solve the original game as well as all four Hasbro variants mentioned above. It is impossible to play against it because that is not my original intention.

It utilizes bitboards to represent Connect Four which is much more efficient in manipulation than arrays. Additionally, pointers and unions are applied to reduce the memory footprint for this data structure.

Currently, it uses negamax with alpha-beta pruning, static move ordering, and transposition tables to obtain the optimum solution given a state. Opening databases are partially implemented and are inefficient for large databases at the moment.

The playing field is not restricted to the standard seven columns by six rows. It can accept sizes from 4x4 to about 11x10 due to how finite bitboards works, but the maximum is 16. By default, Four the Win! operates on the standard size without arguments. More details about how to use them are under the Arguments heading. 

## Compilation Instructions
I have attached a Makefile for easy compiling on Linux as any C99+ compiler and GNU Make are the only dependencies required. I recommend GCC for compilation. Open a terminal emulator of your choice and type the following commands below
```
git clone https://github.com/TheTrustedComputer/Four-The-Win
cd Four-The-Win
make
```
This should create an executable binary called FourTheWin in the same directory it compiled. Run it with
```
./FourTheWin
```
and enjoy!

Windows users need at least Visual Studio 2019 Community to compile Four the Win! on their platform. Instructions on that later.

I do not own an Apple computer. If you have a Mac and wanted to try out Four the Win!, then please post compilation instructions for those users on the issue tab.

## Arguments
To be announced.

## Contribution and Bug Reporting
Four the Win! is in alpha and is mostly working as intended. Feel free to contribute since I am still working on this project although slowly. If you find any bugs in my program, please open an issue, and I will attempt to debug them. It is not guareteed I will fix all given issues in a timely manner.
