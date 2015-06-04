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

## iostat
Storage devices I/O statistics
```
> iostat -xx 1
avg-cpu:  %user   %nice %system %iowait  %steal   %idle
           0.66   11.35    0.86    0.19    0.00   86.94

Device:         rrqm/s   wrqm/s     r/s     w/s   rsec/s   wsec/s avgrq-sz avgqu-sz   await  svctm  %util
sda               0.00     3.60    1.91    4.86    89.65  2579.38   394.05     0.43   63.05   3.58   2.43
dm-0              0.00     0.00    0.90    0.03    30.11     2.71    35.11     0.00    2.01   0.70   0.07
dm-1              0.00     0.00    0.96    3.04    57.69   821.66   219.76     0.31   77.14   2.39   0.96
dm-2              0.00     0.00    0.04    1.96     1.72    20.11    10.90     0.01    6.50   2.83   0.57
dm-3              0.00     0.00    0.00    3.19     0.01  1734.88   543.18     0.20   63.84   4.34   1.39
dm-4              0.00     0.00    0.00    0.00     0.01     0.02     8.08     0.00    2.83   1.85   0.00
```

## systat
Network interface throughput, TCP statistics etc.
```
> systat -ifstat
```
