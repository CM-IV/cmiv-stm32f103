# From Design to Debug: Building My Custom STM32F103 PCB

![](https://i.postimg.cc/vB7kvs6J/cmiv-stm32f103c8.png)

### Introduction
A few months ago, my entire embedded systems experience boiled down to collecting temperature and accelerometer data on an ESP32-C3 dev board using Rust. Coming from a computer science background, I’d written my fair share of JavaScript and C++ code, but hardware always felt like a black box—until I decided to pry it open. Rust’s strict compiler and fearless concurrency made embedded development less intimidating for me; no more worrying about whether my pointers were corrupting memory or if my ISRs would deadlock. But writing firmware for a pre-built dev board only showed me half the picture.

I wanted to understand the why behind the hardware: why I²C demands pull-ups and why my carefully written Rust code would fail if the PCB layout was wrong. So I designed my own 2-layer STM32F103 breakout board in KiCAD 9 (on GNU/Linux, of course), with pinouts for SWD, UART, I²C, and GPIO. It was a crash course in humility. I learned the hard way that LCSC’s inventory doesn’t care about my schematic’s optimism—footprint reviews and BOM checks aren’t just best practices. They’re the difference between a working board and a soldering session.
## Design
I went with the STM32F1 since it's cheap and has the peripherals I need.  It's the ARM Cortex-M3 series of MCU.  Initially, I started laying out the power delivery section of the schematic with the necessary 100nF and 10uF decoupling capacitors(C1-C8)—one for every VDD pin on the IC.  I also went with a 120Ω ferrite bead (FB1) to act as a filter for clean power on the analog side of things.  You'll see that these capacitors and the ferrite bead are placed very close to the IC looking at the board layout later on.

![power delivery](https://i.postimg.cc/HWyV8Kq9/pwr-deliv.png)


## Assembly
## Validation and Testing
## Lessons Learned
## Next Steps
