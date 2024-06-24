## Mega Mount
![megaMount 3d](/assets/megaMount-rendered.png)
[Mega Mount repo](https://github.com/Bortle-Space/Mega-Mount)
### Technical Specs
- Gear Ratio ~40:1
- Microstepping: 1/256
- Step Angle 1.8 Degrees
- Drivers: Closed loop direct mounted drivers. 
- Payload Capacity: ?
- DS3231 RTC for timing pules for right ascension tracking.

### Embedded Control System
The mount uses a custom PCB fitted with an Arduino Mega to drive the axis, and act as a base for the entire astrophotography system. Autofocus is implemented using a similar Stepper driver to the Nema 23's.
![megaMount PCB](/assets/megaMount-pcb-render.png)

Not implemented in the control software *yet*:
- Filter wheel control
- Temperature monitoring and reporting
- Current monitoring and reporting.
- Hall Effect positioning.

Commands are sent to the mount via Serial communication from a host PC or another microcontroller. They take the following format:
`E-27000;`
`E` is for equitorial axis.
`-27000` is the amount to move(arcseconds)
`;` end of command character.

The same can be used with `F`ocus and `D`eclination as well. In addtion to this there are also several `G`eneral commands in the software.

*Update With General Commands*