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
<<<<<<< HEAD

style +5V fill:orange
style +3V3 fill:red
style SDA fill:blue
style SCL fill:white
style GND fill:black

Uno_3V3 -.- +3V3 -.- L75_VCC
Uno_5V --- +5V --- L75_VCC
Uno_A4 --- SDA --- L75_SDA
Uno_A5 --- SCL --- L75_SCL
Uno_GND ---GND --- L75_GND
```
