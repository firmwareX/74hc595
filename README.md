# 74HC595

SR Pins

![](./SR.jpg)

ESP32c3 Demo

```python
from machine import Pin, SPI,SoftSPI
from spi74hc595 import SR
from float2pins import float2pins

#spi = SPI(1, 100000)
spi = SoftSPI(baudrate=800000, polarity=1, phase=0, sck=Pin(2), mosi=Pin(10), miso=Pin(4))

rclk = Pin(7, Pin.OUT) #loadpin cs
sr = SR(spi, rclk, 3) #LEDs total

def clear():
  sr[0]=0xff
  sr[1]=0xff
  sr[2]=0xff

clear()
float2pins(36.5)
```
# 74hc595
