# smoothieonsbase
Smoothieware firmware configs for a D-Bot on a MKS Sbase board. I am using 0.9 degree steppers.

## Steppers used

All my steppers are 17HM19-2004S Nema 17 steppers. These are 0.9 degree, 46Ncm torque, 2A at 2.8V, 42x42x48mm with 4 wires.

I purchased mine from www.omc-stepperonline.com.

They come with hard wired cables into the stepper motors, the wiring pairs being Black/Green, and Red/Blue.

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

I am using an E3D v6 all metal clone with a short heatsink, and a RepRap 330x330 bed. From the telnet console, perform the tuning specified at http://smoothieware.org/temperaturecontrol#pid-autotuning

## Extruder drive

I abandoned the long bowden setup for a Flex3drive Dual Nozzle unit. Dual print heads, flexible remote drive cable, and a very light hot end. No speed loss, with the benefits of a direct drive. 

## Firmware image

`FIRMWARE.CUR` is my presently running image, based on Smoothieware edge 773459d from the 25th of October 2018. Rename it to firmware.bin, and reset the board to flash it.
