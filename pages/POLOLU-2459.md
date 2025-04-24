---
title: "POLOLU-2459"
---

- [[Photo Reflector]]
It can be read by RasPi without ADC because of digital output, but instead of watching ON/OFF by GPIO voltage, it is used to measure the time from outputting HI to reading and then back to LO.

- Set the I/O line to an output and drive it high.
- Allow at least 10 μs for the sensor output to rise.
- Make the I/O line an input (high impedance).
- Measure the time for the voltage to decay by waiting for the I/O line to go low.
[Pololu - QTR-1RC Reflectance Sensor (2-Pack)](https://www.pololu.com/product/2459)

- It might be a good idea to use it on an Arduino with a set of libraries put out by the manufacturer.
- I thought, "It's a digital output, so even a RasPi without an ADC will work!" but it's a pain in the ass!

It's usable in one way or another [source code](https://gist.github.com/nishio/8dd862a127b0d8045d23aac90c9c9b27).

---
This page is auto-translated from [/nishio/POLOLU-2459](https://scrapbox.io/nishio/POLOLU-2459) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.