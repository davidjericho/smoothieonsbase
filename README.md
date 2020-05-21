# smoothieonsbase
Smoothieware firmware configs for a D-Bot on a MKS Sbase board.

## Stepper order

The left stepper motor is plugged into the X socket.
The right stepper motor is plugged into the Y socket.

## Stepper wirings

The Y motor is wired as:

| Colour | Board pin |
| ------ | --------- |
| Black | 2B |
| Green | 2A |
| Red | 1A |
| Blue | 1B |

The X motor is wired as:

| Colour | Board pin |
| ------ | --------- |
| Blue | 2B |
| Red | 2A |
| Green | 1A |
| Black | 1B |

The Z steppers are wired in series.

Following the wiring order from the Y motor plug, the connections flow:

| Start connection | End connection |
| ---------------- | -------------- |
| Black on plug | Black on stepper one |
| Green on stepper one | Black on stepper two |
| Green on stepper two | Green on plug |
| Red on plug | Red on stepper one |
| Blue on stepper one | Red on stepper two |
| Blue on stepper two | Blue on plug |

## Pid override tunings

Thermistor for the hotend is a 100K thermistor - ATC Semitec 104GT-2. From the telnet console, perform the tuning specified at http://smoothieware.org/temperaturecontrol#pid-autotuning

## Extruder drive

E3D Titan Aero.

## LCD configuration

I am using a Makerbase TFT32 with this board.

## Firmware image

`FIRMWARE.CUR` is my presently running image, from Smoothieware edge 8f9be6f from the 21st of May 2020. Rename it to firmware.bin, and reset the board to flash it. Smoothieware is GPLv3, and the compiled source origin for this binary is https://github.com/Smoothieware/Smoothieware/commit/8f9be6f801d723a86dfef1dfae6bc975572da2a2

Copy config.txt to the SD card along side the firmware.bin file, and the printer will use this as configuration.

See http://smoothieware.org/sd-card for SD card information.
