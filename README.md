# KernelUNOwithSD v1.0

A fork of KernelUNO by [Arc1011](https://github.com/Arc1011/KernelUNO), with the RAM filesystem replaced with access to a filesystem on an SD card. The commands for interacting with the filesystem now use the Arduino SD library. There's no dev directory or find command in this version, but besides that i tried to keep it as close to the original as possible.
The pins to connect the Arduino to the SD card are the standard pins for the UNO SD library:
CS - pin 10
SDO - pin 11
SDI - pin 12
CLK - pin 13

<img width="769" height="659" alt="554" src="https://github.com/user-attachments/assets/82aa5f0c-bf22-4f83-865a-ba3b4258011e" />


# Commands (26):

- `ls`
- `cd`
- `pwd`
- `mkdir`
- `touch`
- `cat`
- `echo`
- `rm`
- `info`
- `pinmode`
- `write`
- `read`
- `gpio`
- `pwm`
- `sh`
- `uptime`
- `uname`
- `dmesg`
- `df`
- `free`
- `whoami`
- `clear`
- `reboot`
- `alias`
- `slots`

## How It Works

The code now manages a filesystem stored on an SD card connected via SPI, allowing for greater capacity than the RAM of the Arduino. KernelUNOwithSD can read files of any length, but length of content written to files and maximum file path are still limited by RAM.

GPIO control uses standard Arduino functions: `pinMode()`, `digitalWrite()`, `digitalRead()`, and `analogWrite()`.

Input is buffered from the serial connection and parsed line-by-line. Commands are case-insensitive.

## License

BSD3 - Original by [Arc1011](https://github.com/Arc1011/KernelUNO)

