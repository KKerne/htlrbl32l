# Key Provisioner Firmware

This document has the objective of instructing the use of the Key Provisioner Firmware, meant to be run on the first contact with a HTLBL32L chip. If you have not opted for the hardware secure module version or do not intend to use it, you can skip this document.
By using this firmware, you will be able to set all the required LoRaWAN keys (both OTAA or ABP) through serial AT commands. These keys will then stay safely stored within our secure module, not being able to be read by anyone except HTLRBL32L’s crypto library. Note: You can overwrite any of the LoRaWAN keys written on the device, but you cannot retrieve them.

## Step-by-step configuration
 - Flash the [Firmware](https://github.com/KKerne/htlrbl32l/blob/SDK/Documentation/Firmware%20Flashing.pdf)
 - Configure the [Serial](https://github.com/KKerne/htlrbl32l/blob/SDK/Documentation/Firmware_Flashing_and_config.md)
 - Configure [Termite](https://github.com/htmicron/htlrbl32l/blob/SDK/Examples/Applications/LoRaWAN-Base/Termite_Setup.png)

## Command List

You can run these commands in any order and rewrite them if needed. It is mandatory to enter the DevEui command and the keys referred to your chosen activation type (ABP or OTAA). 
You don’t need to enter keys for the activation mode you’re not planning to use. 

| **Command**       | **Parameter**             | **Description**                                                                                                     |
| ----------------- | ------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| AT+DEVEUI=<param> | 16 charactere hexadecimal | [Sets the unique DevEUI](https://lora-developers.semtech.com/documentation/tech-papers-and-guides/the-book/deveui/) |

### ABP Keys commands

ABP keys configuration is not required when using OTAA activation mode.

| **Command**             | **Parameter**             | **Description**  |
| ----------------------- | ------------------------- | ---------------- |
| AT+ABP_DEVADDR\=<param> | 8 charactere hexadecimal  | Sets the DevAddr |
| AT+ABP_APPSKEY=<param>  | 32 charactere hexadecimal | Sets the AppSKey |
| AT+ABP_NWKSKEY=<param>  | 32 charactere hexadecimal | Sets the NwkSKey |

### OTAA Keys Commands

OTAA keys configuration is not required when using ABP activation mode.

| **Command**             | **Parameter**             | **Description** |
| ----------------------- | ------------------------- | --------------- |
| AT+OTAA_JOINEUI=<param> | 16 charactere hexadecimal | Sets the AppEUI |
| AT+OTAA_APPKEY=<param>  | 32 charactere hexadecimal | Sets the AppKey |

## Return Codes

Every command returns a 4 byte code, the first two bytes are represented by the tables below. Bytes 3 and 4 are unused. 
You can check how Error Codes works in this [link](https://github.com/htmicron/htlrbl32l/blob/SDK/Examples/Applications/HTLRBL32L-AT-Commands/Documentation/Error_codes.md)
