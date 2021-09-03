# My Pomodoro Timer

I'm always changing my duration on my Pomodoro timer. The "standard" is
25 minutes with five minute breaks and a fifteen minute break every 4
sessions, but that doesn't always work out with meetings and coding
sessions. In fact, there's good science that contradicts the conclusion
to always use 25 minutes, that it can break an otherwise amazing flow
state in the middle. I'm going with top of the hour starting sessions
and 15 minute breaks before the next hour starts. That's enough time to
do some sun salutations, take some notes about what was accomplished,
and make coffee. The 25/5 thing is just way to ADD for me.

In fact, in `pomo` tool I'll be building in different modes:

* `scheduled` mode that uses a set schedule
* `normal` mode that just starts when you start it

There will be configuration settings to manage the durations and
intervals:

* `duration.session` (default: 4)
* `duration.break.short` (default: 25)
* `duration.break.long` (default: 35)
* `sessions.per.block` (default: 4)

Scheduled mode uses the `schedule` configuration parameters for the
week: `mon`, `tue`, `wed`, `thu`, `fri`, `sat`, `sun`. Each takes a
space-delimited list of sessions by 24-hour clock with an optional
duration in minutes and an at sign (`@`) prefixed. If there is no prefix
the `duration.session` is assumed. The interval between the end of a
session and the beginning of a start times is assumed to be `break`
time.

```
mon=9 10 13
sun=45@10 90@16
```

References:

* The Pomodoro Technique --- Why It Works & How To Do It
  <https://todoist.com/productivity-methods/pomodoro-technique>

Tags:

    #pomodoro #timemanagement #lifehacks
