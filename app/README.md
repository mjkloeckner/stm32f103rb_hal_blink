# Non-blocking app template

This is a template of a bare metal, event triggered application that runs tasks
secuentally for STM32 boards using HAL library, in particular STM32F103RB on
NUCLEO-F103RB board.

## Files

### `app.*`

Endless loops, which execute tasks with fixed computing time. This 
sequential execution is only deviated from when an interrupt event occurs.
Cyclic Executive (Update by Time Code, period = 1mS)

### `task_sensor*`

Non-Blocking & Update By Time Code -> Sensor Modeling

### `task_system*`

Non-Blocking Code -> System Modeling

### `task_system_interface.*`

Non-Blocking Code

### `task_actuator*`

Non-Blocking & Update By Time Code -> Actuator Modeling

### `task_actuator_interface.*`

Non-Blocking Code

### `logger.*`

Utilities for Retarget "printf" to Console

### `dwt.h`

Utilities for Mesure "clock cycle" and "execution time" of code

### `systick.*`

Utilities for delay "microseconds"
