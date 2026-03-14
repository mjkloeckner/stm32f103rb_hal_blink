# Stm32 blink example

## Execution stack

The main loop calls the main app and then this app executes the tasks
secuentially in order

```text
app
`- task_sensor
`- task_system
`- task_actuator
```

## Debug

In Stm32CubeIDE Project Explorer view right click over the project, then debug
configurations. In Debugger tab set Debug probe as ST-LINK (OpenOCD) and after
pressing Show generator options setupReset Mode as Software system reset.
In Startup tab add 'monitor arm semihosting enable' to the initialization
commands. Finally Apply and Close (or Debug).
