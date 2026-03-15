# Non-blocking blink example

This is an example/template of a bare metal, event triggered application that
runs tasks secuentally for STM32 boards using HAL library, in particular
STM32F103RB on NUCLEO-F103RB board.

## Execution stack

The main loop calls the main app and then this app executes the attached tasks
secuentially in order: `task_sensor`, `task_system` and `task_actuator`.

## Debug

In Stm32CubeIDE Project Explorer view right click over the project, then debug
configurations. In Debugger tab set Debug probe as ST-LINK (OpenOCD) and after
pressing Show generator options setupReset Mode as Software system reset.
In Startup tab add 'monitor arm semihosting enable' to the initialization
commands. Finally Apply and Close (or Debug).

## Running without IDE

By default the code is written to run with the Stm32CubeIDE opened and in debug
mode, this by using semihosting. Semihosting is a way to log to the host console
via the attached debugger (without using an additional serial port). But if a
host console is not detected during initilization the program will halt.

To run code without debug mode or without having the IDE opened semihosting
needs to be disabled. This is done by defining the macro
`LOGGER_CONFIG_USE_SEMIHOSTING` as `0` instead of `1` in the file `app/logger.h`.
