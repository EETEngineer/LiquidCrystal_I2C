# LiquidCrystal_I2C

[![Compile Examples Status](https://github.com/markub3327/LiquidCrystal_I2C/workflows/Compile%20Examples/badge.svg)](https://github.com/markub3327/LiquidCrystal_I2C/actions?workflow=Compile+Examples) [![Spell Check Status](https://github.com/markub3327/LiquidCrystal_I2C/workflows/Spell%20Check/badge.svg)](https://github.com/markub3327/LiquidCrystal_I2C/actions?workflow=Spell+Check)

A comprehensive Arduino library for controlling HD44780-based LCD displays via I2C interface. This library provides full compatibility across all Arduino architectures and platforms.

Character OLED Support

Some HD44780-style "Character OLEDs" require different timings than a normal LCD.
 - OLEDs may show garbage characters after a reset due to their memory not being cleared or initialization timing
 - This is not a problem with normal HD44780 controlled LCD displays
 - Is diabled by default

Using OLED Mode (Arduino Style)

#include <LiquidCrystal_I2C.h>
LiquidCrystal_I2C oled(0x27, 20, 4); //Named object oled, but specific naming is not required

void setup() {
 //Enable OLED Compatibility Mode
 oled.enableOledMode(true, true); //(Oled specific timing, Hard memory clear on init())

 oled.init();
 oled.print("Hello World");
}
