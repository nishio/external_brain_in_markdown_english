---
title: "Ergodox"
---

Compile information about Ergodox EZ for your future self.

- What is this?
    - Keyboard with published schematics and firmware
    - [Teensy USB Development Board](https://www.pjrc.com/teensy/)
    - Atmega32U4
    - Separate right and left hands, I2C for communication between them
        - Physically connected with a 4-pole stereo cable.
        - I think the schematic shows SCL, SDA, and VCC as 1 to 1, but I haven't verified it yet.
        - VCC is 5V
    - I2C expanders on both sides

source
- [https://github.com/jackhumbert/qmk_firmware/tree/master/keyboards/ergodox](https://github.com/jackhumbert/qmk_firmware/tree/master/keyboards/ergodox)

Build Guide [https://github.com/qmk/qmk_firmware/blob/master/docs/BUILD_GUIDE.md](https://github.com/qmk/qmk_firmware/blob/master/docs/BUILD_GUIDE.md)
:

```
$ cd /home/nishio/ergodox/qmk_firmware/keyboards/ergodox
$ make nishio
```


2C related
    - keyboards/ergodox/ez/i2cmaster.h
    - keyboards/ergodox/ez/twimaster.c

schematic
- [https://github.com/ErgoDox-EZ/docs/](https://github.com/ErgoDox-EZ/docs/)
    - The Ergodox EZ board I bought is 2260.
        - I opened it up and checked inside.
            - To open the inside, remove the sticker on the back.

farm-reading comprehension
- keyboard_task
    - [https://github.com/qmk/qmk_firmware/blob/master/tmk_core/common/keyboard.c#L154](https://github.com/qmk/qmk_firmware/blob/master/tmk_core/common/keyboard.c#L154)
c

```c
/*
 * Do keyboard routine jobs: scan mantrix, light LEDs, ...
 * This is repeatedly called as fast as possible.
 */
void keyboard_task(void)
{...
```

    - I'm calling `matrix_scan();` all over the place in
- matrix_scan
    - [https://github.com/qmk/qmk_firmware/blob/master/keyboards/ergodox/ez/matrix.c#L174](https://github.com/qmk/qmk_firmware/blob/master/keyboards/ergodox/ez/matrix.c#L174)
    - I'm trying to challenge the connection to see if the keyboard on the left side is connected.
c

```c
uint8_t matrix_scan(void)
{
    if (mcp23018_status) { // if there was an error
        if (++mcp23018_reset_loop == 0) {
            // since mcp23018_reset_loop is 8 bit - we'll try to reset once in 255 matrix scans
            // this will be approx bit more frequent than once per second
            print("trying to reset mcp23018\n");
            mcp23018_status = init_mcp23018();
            if (mcp23018_status) {
                print("left side not responding\n");
            } else {
                print("left side attached\n");
                ergodox_blink_all_leds();
            }
        }
    }
```

- init_mcp23018
    - [https://github.com/qmk/qmk_firmware/blob/master/keyboards/ergodox/ez/ez.c#L50](https://github.com/qmk/qmk_firmware/blob/master/keyboards/ergodox/ez/ez.c#L50)

- deley's way of doing things
c

```c
_delay_ms(50);
```


- debug console
    - [https://github.com/tmk/tmk_keyboard/wiki/FAQ#debug-console](https://github.com/tmk/tmk_keyboard/wiki/FAQ#debug-console)
    - CDC
        - [http://www.recursion.jp/prose/avrcdc/driverj.html](http://www.recursion.jp/prose/avrcdc/driverj.html)
        - R232C runs on top of USB
    - debug console
        - [https://www.pjrc.com/teensy/hid_listen.html](https://www.pjrc.com/teensy/hid_listen.html)
    - Device not found
        - If you read the source, hid = rawhid_open_only1(0, 0, 0xFF31, 0x0074); then read.
            - Here's the implementation of this
                - [https://github.com/raphendyr/teensy-listen/blob/master/rawhid.c#L71](https://github.com/raphendyr/teensy-listen/blob/master/rawhid.c#L71)

- LED Debugging
    - ergodox_right_led_1_on();
    - ergodox_led_all_off();
    - ergodox_led_all_set(LED_BRIGHTNESS_HI);


- Right side only, half of 1 is attached in normal connection
    - 1 disappears when the cable is unplugged.
        - Then it doesn't come back.
- Start only on the right side, and when the breadboard is inserted, 1 disappears.
c

```c
void init_7seg(void)
{
  ergodox_led_all_off();
  ergodox_led_all_set(LED_BRIGHTNESS_HI);
  i2c_init();
  ergodox_right_led_2_on();
  i2c_start(0x70);
  ergodox_right_led_3_on();

  i2c_write(0x21);
  i2c_stop();
  _delay_ms(10);

  i2c_start(0x70);
  i2c_write(0x81);
  i2c_stop();
  _delay_ms(10);

  i2c_start(0x70);
  i2c_write(0xEF);
  i2c_stop();
  _delay_ms(10);
  ergodox_right_led_1_on();
}

```


- TRRS
    - Grand seems to be right.
    - Four buses with branches have been verified to have correct continuity to four
        - I put them in TRRS order, green-black-green-black, with stickers on 1 and 2.
    - It will not function as an I2C bus with only VCC and GND connected to the LEDs.
    - GND seems to be right.
        - When VCC is pointed to 3, the bus will not function.
        - Returns when pulled out.
        - When pointed to 2, it stops functioning and does not come back when unplugged.
        - The bus functions when pointed to 1.
            - One step forward!
    - I've kicked it from Raspi and confirmed that the 7 seg is still alive.
    - Connected Raspi to left hand keyboard and i2cdetect -y 1 and confirmed I'm at 0x20
        - SDA is 2 at this time.
        - Wired accordingly and confirmed that i2cdetect finds 0x20 and 0x70

Direct LED operation with registers
- LED 1 ON
    - inline void ergodox_right_led_1_on(void)    { DDRB |=  (1<<5); PORTB |=  (1<<5); }
- LED 2
    - DDRB |=  (1<<6); PORTB |=  (1<<6);
- LED 3
    - DDRB |=  (1<<7); PORTB |=  (1<<7);

logic analyzer
- It's off by 1 bit.



- Key map cheat sheet [http://qiita.com/ReSTARTR/items/970354940f49c67fb9fd](http://qiita.com/ReSTARTR/items/970354940f49c67fb9fd)
- [https://www.pjrc.com/teensy/loader_cli.html](https://www.pjrc.com/teensy/loader_cli.html)
- Using Macros with ErgoDox - Qiita
    - [http://qiita.com/teri_yakichan/items/db54589b67ba9330faed](http://qiita.com/teri_yakichan/items/db54589b67ba9330faed)
- Let's set up 💥🍣emoji key🍣💥 - Qiita
    - [http://qiita.com/miyaoka/items/969864e5219349f01be3](http://qiita.com/miyaoka/items/969864e5219349f01be3)
- I2C
    - [https://github.com/benblazak/ergodox-firmware/blob/master/src/lib/twi/teensy-2-0.c](https://github.com/benblazak/ergodox-firmware/blob/master/src/lib/twi/teensy-2-0.c)

---
This page is auto-translated from [/nishio/Ergodox](https://scrapbox.io/nishio/Ergodox) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.