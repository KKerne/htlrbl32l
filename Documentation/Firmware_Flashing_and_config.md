# Firmware Flashing

 - Flash the [Firmware](https://github.com/KKerne/htlrbl32l/blob/SDK/Documentation/Firmware%20Flashing.pdf)

# Serial Terminal Setup

The UART interface can be used by connecting the pins TX(PA9) and RX(PA8) to a USB-Serial converter and connecting to a computer or simply connecting it to another microcontroller with a UART interface.

UART configuration required to connect:
-	Baud rate: 115200
-	Data bits: 8
-	Stop bits: 1
-	Parity: none
-	Flow Control: none
-	Transmitted text: Append LF

# Termite Setup

One of the most widely used software for UART communication using a computer is Termite.
The required configurations to use it are shown bellow.

![Termite Setup](https://github.com/KKerne/htlrbl32l/blob/SDK/Examples/Applications/LoRaWAN-Base/Termite_Setup.png)
