# Nest Automation

This package will:
1. Enable Eco mode if the weather outside is warmer than the heat setpoint & return to Heat mode if it cools.
1. Provide a temperature offset that can be used to specify a difference in outside temperature (to allow for Eco mode to be set when it is slightly cooler outside than the setpoint)
1. Home/away automation based on device_trackers

## Eco mode in Warm Weather
Firstly, if the operation_mode is set to 'off' this automation will not trigger.

## Logic
I determines the current state and acts as follows:
    
If

- It's warmer outside them the setpoint (allowing for the offset)

    &
- The operation_mode is 'Heat'

Then
- Set 'Eco' mode and set a flag incidating that it was Home Assistant that set it

### However
If

- It's colder outside them the setpoint (allowing for the offset)

    &
- The operation_mode is 'Eco'

    &
- It was Home Assistant that set Eco mode

Then
- Set 'Heat' mode and clear a flag incidating that it was Home Assistant that Eco