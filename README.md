Weather Monitoring System Using 8086 Microprocessor

A hardware-software system built around the Intel 8086 microprocessor that reads and displays real-time temperature, humidity, and atmospheric pressure using an ADC, three LCD displays, and interrupt-driven timing logic programmed entirely in x86 Assembly.


Features

- Reads three sensor channels (temperature, humidity, pressure) via an ADC with multiplexed channel selection
- Displays live readings on three independent 16x2 LCD screens
- Samples every 5 minutes and computes hourly rolling averages across 12 stored readings
- Button-triggered interrupt for immediate on-demand sensor refresh
- Interrupt-driven architecture using the 8259 PIC, 8255 PPI, and 8253 PIT
- Sensor scaling: temperature (-50 to 50 C), humidity (0-99%), pressure (0.4-1.1 Bar)


Hardware Components

- Intel 8086 Microprocessor
- 8259 Programmable Interrupt Controller (PIC)
- 8255 Programmable Peripheral Interface (PPI) — I/O port management
- 8253 Programmable Interval Timer (PIT) — 5-minute and 1-hour timing pulses
- ADC (Analog-to-Digital Converter) — 8-bit, 3-channel
- 3x 16x2 LCD displays


Interrupt Structure

- ISR0 (Button)     — sets an update flag for immediate sensor read
- ISR1 (5-minute)   — triggers ADC conversion for all three sensor channels
- ISR2 (1-hour)     — computes average of stored readings and updates LCD display
- ISR3 (EOC)        — reads ADC output on End-of-Conversion signal and stores the value


Tools

- x86 Assembly
- EMU8086 (Emulator/Simulator)


Note

Hardware design and circuit documentation are available in Manuals/Hardware_design.pdf. Full project report is in Manuals/MUP Group Project.pdf.
