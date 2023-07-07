# Documentation

## Blueretro implementation

Check out the Project [Constraint File](../src/NES_TN9.cst), but if you won't build from source or do any modifications you can make this wiring:

| Tang Nano 9k | ESP32 | Dualshock 2 Interface |
|:---:|:---:|:---:|
|25|D33|CLOCK|
|26|D32|COMMAND|
|27|D19|DATA|
|28|D34|ATTENTION|

## ROM Flashing

Just binary write the NES rom (in [iNES](https://www.nesdev.org/wiki/INES) format) into the microSD card in raw data.

If you flash using [dd](https://en.wikipedia.org/wiki/Dd_%28Unix%29) command in linux, make sure the entire binary will fit 512 bytes block by padding the remaining space with any data.

I recommend using a binary editor tool as [ImHex](https://github.com/WerWolv/ImHex) or make a script to do that job.

## Build from Source

Needs GoWin Official IDE, just:

1. open the project [gprj](../nestang9k-ps2.gprj) file
2. make the top entity to be `NES_TN9` module
3. select `System Verilog 2007` to be the project synthesizer
4. run Synthesize, then Place and Route tools
5. flash the `.fs` file