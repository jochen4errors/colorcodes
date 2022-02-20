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
  Uno_3V3-.-|orange|L75_VCC
  Uno_5V-.-|red|L75_VCC
  Uno_A4---|blue|L75_SDA
  Uno_A5---|white|L75_SCL
  Uno_GND---|black|L75_GND
  Battery_V(+9v)===|violet|Uno_Battery_Plug+(+V)
  Battery_GND(GND)===|black|Uno_Battery_Plug-(GND)
  
  subgraph "🌡️ LM75"
    L75_VCC(VCC)
    L75_GND(GND)
    L75_SDA(SDA)
    L75_SCL(SCL)
  end

  subgraph "Arduino Uno"
    Uno_3V3(3V3)
    Uno_5V(5V)
    Uno_GND(GND)
    Uno_A4(A4)
    Uno_A5(A5)
    Uno_Battery_Plug+(+V)
    Uno_Battery_Plug-(GND)
  end

  subgraph "🔋 Battery"
    Battery_V(+9v)
    Battery_GND(GND)
  end
```

## Example ADC (ADS1115)

```mermaid
  flowchart LR
    Uno_3V3(3V3)-.-|orange|ADS1115_VDD(VDD) 
    Uno_5V(5V)-.-|red|ADS1115_VDD(VDD)
    Uno_5V(5V)---|red|SensorVCC(VCC)
    Uno_GND(GND)-----|black|ADS1115_GND(GND)
    Uno_GND(GND)-----|black|SensorGND(GND)
    Uno_A4(A4)---|blue|ADS1115_SDA(SDA)
    Uno_A5(A5)---|white|ADS1115_SCL(SCL)
    ADS1115_A0(A0)---|"brown 🌡️"|Sensor1(Temperature)
    ADS1115_A1(A1)---|"brown 💦"|Sensor2(Humidity)

    subgraph Analog Sensor
      SensorVCC(VCC)
      SensorGND(GND)
      Sensor1(Temperature)
      Sensor2(Humidity)
    end

    subgraph ADS1115
      ADS1115_VDD(VDD)
      ADS1115_VDD(VDD)
      ADS1115_GND(GND)
      ADS1115_SDA(SDA)
      ADS1115_SCL(SCL)
      ADS1115_A0(A0)
      ADS1115_A1(A1)
    end

    subgraph Arduino Uno
      Uno_3V3(3V3)
      Uno_5V(5V)
      Uno_GND(GND)
      Uno_A4(A4)
      Uno_A5(A5)
    end
```
