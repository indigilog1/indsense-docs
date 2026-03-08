# Operation Protocol

## Function Code

| Function Code | Description          | Note                  |
|---------------|----------------------|-----------------------|
| 01            | Read Coil Status     | Read relay status     |
| 05            | Write Single Coil    | Write Single Relay    |
| 0F            | Write Multiple Coils | Write Multiple Relays |

## Register Address

| Address (HEX)              | Description       | Register Value                         | R/W        | Function Code    |
|----------------------------|-------------------|----------------------------------------|------------|------------------|
| 0x0000<br/>....<br/>0x0011 | Relay 1~4 address | 0x0000: Relay OFF<br/>0xFF00: Relay ON | Read/Write | 0x01, 0x05, 0x0F |

## Control Single Relay

Command: 01 05 00 00 FF 00 8C 3A

| Field | Description      | Note                                                                         |
|-------|------------------|------------------------------------------------------------------------------|
| 01    | Device ID        | 0x00 indicates the broadcast address, 0x01-0xFF indicates the device address |
| 05    | Function Code    | Relay Control                                                                |
| 00 00 | Register Address | The register address of the relay, 0x0000 - 0x0011                           |
| FF 00 | Command          | 0xFF00: Relay ON<br/>0x0000: Relay OFF                                       |
| 8C 3A | Checksum         | CRC16 Checksum of first 6 bytes                                              |

Return Code: 01 05 00 00 FF 00 8C 3A

Commands for every relay

```commandline
Relay 0 ON:         01 05 00 00 FF 00 8C 3A
Relay 0 OFF:        01 05 00 00 00 00 CD CA
Relay 1 ON:         01 05 00 01 FF 00 DD FA
Relay 1 OFF:        01 05 00 01 00 00 9C 0A
Relay 2 ON:         01 05 00 02 FF 00 2D FA
Relay 2 OFF:        01 05 00 02 00 00 6C 0A
Relay 3 ON:         01 05 00 03 FF 00 7C 3A
Relay 3 OFF:        01 05 00 03 00 00 3D CA
```
## Read Relay Status

