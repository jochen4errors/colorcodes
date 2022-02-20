# Wires for Arduino & Co.

| Color  |Voltage  |Signal |I²C|SPI |UART|ISP |
|--------|:-------:|:-----:|:-:|:--:|:--:|:--:|
|red     |+5V      |       |   |    |    |    |
|orange  |+3.3V    |       |   |    |    |    |
|yellow  |+12V     |       |   |    |    |    |
|violet  |any other|       |   |    |    |    |
|black   |GND      |       |   |    |    |    |
|white   |         |Clock  |SCL|SCLK|    |SCK |
|blue    |         |out    |SDA|MOSI|Tx  |MOSI|
|green   |         |in     |   |MISO|Rx  |MISO|
|grey    |         |digital|   |¬SS |    |RST |
|brown   |         |analog |   |    |    |    |


## Example: L75

```mermaid
flowchart LR;
Uno_3V3 -.-|orange| L75_VCC
Uno_5V ---|red| L75_VCC
Uno_A4 <-->|blue| L75_SDA
Uno_A5 -->|white| L75_SCL
Uno_GND ---|black| L75_GND
```
