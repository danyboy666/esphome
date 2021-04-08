# esphome

Custom repo for stuff I need to remember

The yaml is a working base setup for an LCD display interfaced with a matrix keypad hooked up to a PCF8574 board.

Use with https://github.com/ssieb/custom_components/tree/master/keypad

Install componant in /cconfig/esphome/custom_componant/keypad

Thanks to https://github.com/ssieb/custom_components/issues/11#issuecomment-815260903 i ws able to put a working setup together

Relevant lines:

i2c:
  sda: D2
  scl: D1
  scan: False

pcf8574:
  - id: 'pcf8574_hub'
    address: 0x20
    pcf8575: False

keypad:
  id: mykeypad
  rows:
    - pin:
        pcf8574: pcf8574_hub
        number: 0
        mode: OUTPUT
        inverted: False
    - pin:
        pcf8574: pcf8574_hub
        number: 1
        mode: OUTPUT
        inverted: False        
    - pin:
        pcf8574: pcf8574_hub
        number: 2
        mode: OUTPUT
        inverted: False
    - pin:
        pcf8574: pcf8574_hub
        number: 3
        mode: OUTPUT
        inverted: False
  columns:
    - pin:
        pcf8574: pcf8574_hub
        number: 4
        mode: INPUT
        inverted: False
    - pin:
        pcf8574: pcf8574_hub
        number: 5
        mode: INPUT
        inverted: False
    - pin:
        pcf8574: pcf8574_hub
        number: 6
        mode: INPUT
        inverted: False
    - pin:
        pcf8574: pcf8574_hub
        number: 7
        mode: INPUT
        inverted: False
  keys: "123A456B789C*0#D"

logs:

https://pastebin.com/nyhshA6C
