# emwi-wiring
Wiring like device interface for Embedded Wizard GUI projects

This project contains an Embedded Wizard unit, written in chora and inline native C code, which allows the use of the Arduino
connector on the STM32F746NG-DISCO board in a similar manner to simple Arduino code. The unit implements a basic subset of
Arduino's Wiring functions, giving the opportunity for a developer to quickly assemble a GUI interface interacting also
with shields connected to the Arduino connector, without the need to implement middleware in C code and to hassle with
the low level build environment.

This unit is intended primarily for educational purpose, with the scope of teaching students of GUI development for
embedded systems without the need to dig into the inner workings of the microcontroller. For real-life projects it would
indeed be much more efficient to write directly the low level code in C, and create corresponding interfaces in chora,
but when the main focus is on GUI and UX development, the quick turnaround time can bring it's own benefits, just like
the Arduino ecosystem does.

The source code for this Wiring unit can be found in the [src](src) folder, and can be added to an Embedded Wizard project
being fully ready to use with the build environment provided by TARA Systems for the STM32F746 platform package.
The free limited edition of Emebedded Wizard can also be used for small educational projects. A few example projects
are also included in the [tests/examples](tests/examples) folder.

Currently the following core functions are implemented:
- **pinMode**
- **digitalWrite**
- **digitalRead**

To use this functions a chora object (a singleton autoobject with a reference permanently kept in the application is
recommended) must be instantiated in the application, and the core functions called from within this object.
A more chora-oriented approach with properties and slots can also be accessed from the underlining Pins classes.
