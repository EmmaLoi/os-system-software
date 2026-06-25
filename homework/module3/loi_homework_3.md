# Домашнє завдання №3. Процеси та керування ресурсами
Лой Еммануель Ігорівна

## Завдання 1. Огляд активних процесів
```
➜  ~ ps aux
USER               PID  %CPU %MEM      VSZ    RSS   TT  STAT STARTED      TIME COMMAND
emmaloj          19554  74.0  0.2 426963264  16480   ??  Rs   Mon09PM 270:15.93 /System/Library/
_windowserver      372  24.8  0.8 413529424  64640   ??  Ss    6Jun26 564:09.17 /System/Library/
emmaloj            933   8.3  0.8 462280672  67680   ??  S     6Jun26 180:53.82 /Applications/Go
emmaloj          45146   6.9  6.5 1924628048 545328   ??  S     7Jun26 109:50.17 /Applications/Go
root   
/sbin/launchd
emmaloj          43386   3.9  0.5 412325248  43696   ??  S     8Jun26   2:13.36 /System/Applicat
emmaloj            647   3.7  0.4 412030144  36208   ??  R     6Jun26  17:50.73 /System/Library/
emmaloj          15426   2.6  0.2 411152736  17344   ??  Us   Sun09PM  21:25.86 /System/Library/
emmaloj          92134   1.6  0.5 416609984  45072   ??  S     8Jun26 141:28.54 /Applications/zo
emmaloj            559   1.1  0.3 411788704  22592   ??  S     6Jun26   9:34.14 /System/Library/
emmaloj          16239   1.0  0.4 416046464  32784   ??  S    Sun09PM  26:36.17 /Applications/DB
root               342   0.9  0.1 426957696   8256   ??  Ss    6Jun26  15:34.80 /usr/libexec/ope
emmaloj            571   0.5  3.0 512338560 250064   ??  R     6Jun26 220:07.54 /Applications/Go
emmaloj          19545   0.4  0.1 426964928   9360   ??  Ss   Mon09PM   0:10.03 /System/Applicat
emmaloj          19540   0.4  0.1 426960656   8000   ??  Ss   Mon09PM   0:10.78 /System/Library/
emmaloj          92163   0.4  0.1 411603168  11152   ??  S     8Jun26  28:49.39 /Applications/zo
emmaloj           1080   0.4  0.1 1596957008   9536   ??  S     6Jun26   2:53.91 /Applications/Po
emmaloj          19483   0.4  0.1 426965440  12192   ??  S    Mon09PM   5:21.55 /System/Library/
_driverkit         626   0.4  0.4 426906720  31184   ??  Ss    6Jun26  42:46.82 /System/Library/
emmaloj          19552   0.4  0.1 426965472   8000   ??  Ss   Mon09PM   0:09.42 /System/Applicat
emmaloj          19537   0.3  0.1 427036384   8432   ??  Ss   Mon09PM   0:10.16 /System/Library/
root               366   0.3  0.0 426912576   2608   ??  Ss    6Jun26   4:11.80 /usr/sbin/notify
emmaloj          19562   0.3  0.1 426961360   7536   ??  Ss   Mon09PM   0:11.62 /System/Library/
emmaloj          21869   0.2  0.8 1926214480  69584   ??  S    Tue01PM   1:54.86 /Applications/Go
emmaloj          92175   0.1  0.0 410794256   3184   ??  S     8Jun26   0:38.56 /Applications/zo
emmaloj            936   0.1  0.1 1867019520  10064   ??  S     6Jun26  13:31.05 /Applications/Vi
emmaloj            934   0.1  0.7 461366704  56160   ??  S     6Jun26  35:44.74 /Applications/Go
emmaloj          27483   0.1  1.2 1924223824 102800   ??  S    11:19PM   0:00.47 /Applications/Go
emmaloj          44053   0.1  0.9 1924485024  74992   ??  S    Sat01PM   5:07.01 /Applications/Go
root               378   0.1  0.1 426964176   9520   ??  Ss    6Jun26  41:31.69 /usr/libexec/run
```

```
➜  ~ top
Processes: 519 total, 6 running, 513 sleeping, 3456 threads            23:26:56
Load Avg: 5.50, 4.06, 3.70  CPU usage: 29.39% user, 16.68% sys, 53.91% idle
SharedLibs: 211M resident, 63M data, 50M linkedit.
MemRegions: 0 total, 0B resident, 116M private, 583M shared.
PhysMem: 7546M used (1738M wired, 3405M compressor), 89M unused.
VM: 281T vsize, 5536M framework vsize, 70937679(36) swapins, 73852035(0) swapout
Networks: packets: 26428369/25G in, 10414375/3728M out.
Disks: 143632082/2847G read, 54174009/1631G written.

PID    COMMAND      %CPU TIME     #TH   #WQ  #PORT MEM    PURG  CMPRS  PGRP
19554  Applications 96.2 04:32:17 5/1   4/1  81    8801K+ 0B    3008K  19554
28122  ANECompilerS 84.8 01:53.73 3/1   2/1  42    337M+  0B    294M+  28122
```

```
➜  ~ echo $$
28029
```

## Завдання 2. Робота у фоні та керування процесами

```
➜  ~ sleep 1000 &
[1] 28218

➜  ~ jobs
[1]  + running    sleep 1000

➜  ~ fg
[1]  + 28218 running    sleep 1000

[1]  + 28218 suspended  sleep 1000
➜  ~ 

➜  ~ kill -9 28218
[1]  + 28218 killed     sleep 1000                                              
➜  ~ jobs

➜  ~ nohup sleep 500 &
[1] 28257
➜  ~ appending output to nohup.out
```

## Завдання 3. Пріоритети та обмеження

```
➜  ~ nice -n 10 sleep 300 &
[3] 28282

➜  ~ ps -o pid,ni,comm -p $!
  PID NI COMM
28282 15 sleep
```

```
➜  ~ renice 5 -p 28282
renice: 28282: setpriority: Permission denied
```

```
➜  ~ renice 18 -p 28282
ps -o pid,ni,comm -p 28282
  PID NI COMM
28282 18 sleep
```

```
➜  ~ ulimit -a
-t: cpu time (seconds)              unlimited
-f: file size (blocks)              unlimited
-d: data seg size (kbytes)          unlimited
-s: stack size (kbytes)             8176
-c: core file size (blocks)         0
-v: address space (kbytes)          unlimited
-l: locked-in-memory size (kbytes)  unlimited
-u: processes                       1333
-n: file descriptors                256
```

## Завдання 4. Моніторинг ресурсів

```
➜  ~ df -h
Filesystem        Size    Used   Avail Capacity iused ifree %iused  Mounted on
/dev/disk3s1s1   228Gi    17Gi    34Gi    34%    412k  355M    0%   /
devfs            203Ki   203Ki     0Bi   100%     702     0  100%   /dev
/dev/disk3s6     228Gi    10Gi    34Gi    23%      10  355M    0%   /System/Volumes/VM
/dev/disk3s2     228Gi    15Gi    34Gi    31%    1.9k  355M    0%   /System/Volumes/Preboot
/dev/disk3s4     228Gi   747Mi    34Gi     3%     291  355M    0%   /System/Volumes/Update
/dev/disk1s2     500Mi   6.0Mi   483Mi     2%       3  4.9M    0%   /System/Volumes/xarts
/dev/disk1s1     500Mi   5.4Mi   483Mi     2%      40  4.9M    0%   /System/Volumes/iSCPreboot
/dev/disk1s3     500Mi   752Ki   483Mi     1%      43  4.9M    0%   /System/Volumes/Hardware
/dev/disk3s5     228Gi   149Gi    34Gi    82%    854k  355M    0%   /System/Volumes/Data
map auto_home      0Bi     0Bi     0Bi   100%       0     0     -   /System/Volumes/Data/home
/dev/disk3s3     228Gi   2.2Gi    34Gi     7%      88  355M    0%   /Volumes/Recovery
/dev/disk2s1     5.0Gi   2.0Gi   3.0Gi    40%      59   32M    0%   /System/Volumes/Update/SFR/mnt1
/dev/disk3s1     228Gi    17Gi    34Gi    34%    459k  355M    0%   /System/Volumes/Update/mnt1
➜  ~ 
[3]  + 28282 done       nice -n 10 sleep 300
```

```
➜  ~ top -l 1 | grep PhysMem
PhysMem: 7572M used (1628M wired, 3176M compressor), 64M unused.
```
