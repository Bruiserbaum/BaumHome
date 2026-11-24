# Remote Comfort

**Repo:** [ha-remote-comfort](https://github.com/Bruiserbaum/ha-remote-comfort)

## Problem

I'm not always home, and the days I am aren't fixed. The thermostat's own schedule can't tell a remote day from an office day. It doesn't look at the forecast, and with one HVAC unit feeding upstairs and downstairs zones, the upstairs bakes on hot afternoons while downstairs is already cold.

## Approach

- **Schedule by day type.** Remote days, office days, and days off each get their own timeline: wake, work, leave, return, and sleep.
- **Lead times.** Recovery starts before I'm back and before I wake up. It starts earlier when the forecast is extreme.
- **Weather.** On hot days, pre-cool in the morning and don't let the empty house drift too far. Cold days get the mirror image.
- **Rooms with roles.** Bedrooms count at night, the office and living spaces during work hours. Zones with no rooms in use are relaxed.
- **Balancing on a shared unit.** When one zone is far worse than another on the same air handler, the comfortable zone is closed temporarily (setback, or off) so all the air goes where it's needed.
- **Room compensation.** A zone's setpoint is biased so the rooms that matter reach the target, not the hallway where the thermostat hangs.

## My setup

- One air handler with zoned dampers. Each zone shows up in HA as its own `climate.*` entity.
- Room temperature sensors on both floors.
- A weather integration with an hourly forecast.

## Ideas / backlog

- Use a work calendar to decide remote and office days automatically.
- Choose heating or cooling automatically from the forecast during shoulder seasons.
- Learn recovery rates from history instead of using a fixed number of minutes per degree.
- Bias toward cheaper time-of-use electricity windows when pre-cooling.
