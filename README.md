# bgreg-performance
A cheat-sheet of performance-related tools by Brendan Gregg

## uptime
```
> uptime
>  09:26:00 up 11 days, 11:14, 11 users,  load average: 12.06, 6.81, 5.03
```

Primitive, don't spend a lot of time on these.

## top/htop
Simple, can also give weighted CPU load averages

## vmstat
```
> vmstat 1
> 
procs -----------memory---------- ---swap-- -----io---- --system-- -----cpu-----
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
 http://www.slideshare.net/brendangregg/linux-performance-analysis-new-tools-and-old-secrets?related=1
 ...
```
First line shows summary since boot. Then gives high level system summary after every one second (1 is the first argument). The summary includes schedular run queue, syscalls, memory, CPU states
