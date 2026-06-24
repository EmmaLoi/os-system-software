# Домашнє завдання №2. Файлова система і права доступу
Лой Еммануель Ігорівна

## Завдання 1. Ієрархія каталогів Linux

### Кореневий каталог /
```
➜  ~ cd /
ls -la
total 10
drwxr-xr-x  22 root  wheel   704 Jan 16  2025 .
drwxr-xr-x  22 root  wheel   704 Jan 16  2025 ..
lrwxr-xr-x   1 root  admin    36 Jan 16  2025 .VolumeIcon.icns -> System/Volumes/Data/.VolumeIcon.icns
----------   1 root  admin     0 Jan 16  2025 .file
drwxr-xr-x   2 root  wheel    64 Jan 16  2025 .nofollow
drwxr-xr-x   2 root  wheel    64 Jan 16  2025 .resolve
drwxr-xr-x   2 root  wheel    64 Jan 16  2025 .vol
drwxrwxr-x  37 root  admin  1184 Jun 21 21:38 Applications
drwxr-xr-x  68 root  wheel  2176 Jan 18 16:23 Library
drwxr-xr-x@ 10 root  wheel   320 Jan 16  2025 System
drwxr-xr-x   5 root  admin   160 Feb  9  2025 Users
drwxr-xr-x   4 root  wheel   128 Jun 13 21:56 Volumes
drwxr-xr-x@ 39 root  wheel  1248 Jan 16  2025 bin
drwxr-xr-x   2 root  wheel    64 Apr 25  2021 cores
dr-xr-xr-x   4 root  wheel  4837 Jun  6 18:22 dev
lrwxr-xr-x@  1 root  wheel    11 Jan 16  2025 etc -> private/etc
lrwxr-xr-x   1 root  wheel    25 Jun  6 18:22 home -> /System/Volumes/Data/home
drwxr-xr-x   3 root  wheel    96 Dec 15  2021 opt
drwxr-xr-x   6 root  wheel   192 Jun  6 18:22 private
drwxr-xr-x@ 77 root  wheel  2464 Jan 16  2025 sbin
lrwxr-xr-x@  1 root  wheel    11 Jan 16  2025 tmp -> private/tmp
drwxr-xr-x@ 11 root  wheel   352 Jan 16  2025 usr
lrwxr-xr-x@  1 root  wheel    11 Jan 16  2025 var -> private/var
```

### Каталог /etc
```
➜  / cd /etc
➜  /etc ls -la
total 832
drwxr-xr-x  77 root  wheel    2464 Jun 21 20:56 .
drwxr-xr-x   6 root  wheel     192 Jun  6 18:22 ..
-rw-r--r--   1 root  wheel     515 Jan 16  2025 afpovertcp.cfg
lrwxr-xr-x   1 root  wheel      15 Jan 16  2025 aliases -> postfix/aliases
-rw-r-----   1 root  wheel   16384 Jan 16  2025 aliases.db
drwxr-xr-x   9 root  wheel     288 Jan 16  2025 apache2
drwxr-xr-x  16 root  wheel     512 Jan 16  2025 asl
-rw-r--r--   1 root  wheel    1051 Jan 16  2025 asl.conf
-rw-r--r--   1 root  wheel     149 Jan 16  2025 auto_home
-rw-r--r--   1 root  wheel     195 Jan 16  2025 auto_master
-rw-r--r--   1 root  wheel    1932 Jan 16  2025 autofs.conf
-r--r--r--   1 root  wheel     265 Jan 16  2025 bashrc
-rw-r--r--   1 root  wheel    9309 Jan 16  2025 bashrc_Apple_Terminal
-rw-r--r--   1 root  wheel      82 Jan 16  2025 com.apple.screensharing.agent.launchd
-rw-r--r--   1 root  wheel     189 Jan 16  2025 csh.cshrc
-rw-r--r--   1 root  wheel     121 Jan 16  2025 csh.login
-rw-r--r--   1 root  wheel      39 Jan 16  2025 csh.logout
drwxr-xr-x  11 root  _lp       352 Feb  9  2025 cups
-rw-r--r--   1 root  wheel       0 Jan 16  2025 find.codes
-rw-r--r--   1 root  wheel     119 Jan 16  2025 ftpusers
-rw-r--r--   1 root  wheel    5678 Jan 16  2025 gettytab
-rw-r--r--   1 root  wheel    3824 Jan 16  2025 group
-rw-r--r--@  1 root  wheel     213 Jun 21 20:56 hosts
-rw-r--r--   1 root  wheel       0 Jan 16  2025 hosts.equiv
-r--r--r--   1 root  wheel    1299 Jan 16  2025 irbrc
-rw-r--r--   1 root  wheel       0 Jan 16  2025 kern_loader.conf
-rw-------   1 root  wheel    1946 Feb  9  2025 krb5.keytab
lrwxr-xr-x   1 root  wheel      43 May 24 08:19 localtime -> /var/db/timezone/zoneinfo/Europe/Bratislava
-rw-r--r--   1 root  wheel     832 Jan 16  2025 locate.rc
-rw-r--r--   1 root  wheel     106 Jan 16  2025 mail.rc
-r--r--r--   1 root  wheel    2451 Jan 16  2025 man.conf
-rw-r--r--   1 root  wheel      36 Jan 16  2025 manpaths
drwxr-xr-x   2 root  wheel      64 Jan 16  2025 manpaths.d
-rw-------   1 root  wheel    9690 Jan 16  2025 master.passwd
-rw-r--r--   1 root  wheel      53 Jan 16  2025 networks
-rw-r--r--   1 root  wheel    1318 Jan 16  2025 newsyslog.conf
drwxr-xr-x   7 root  wheel     224 Jan 16  2025 newsyslog.d
-rw-r--r--   1 root  wheel      43 Jan 16  2025 nfs.conf
-rw-r--r--   1 root  wheel     557 Jan 16  2025 notify.conf
-rw-r--r--@  1 root  wheel      27 Dec 10  2021 ntp.conf
-rw-r--r--   1 root  wheel      23 Jan 16  2025 ntp_opendirectory.conf
drwxr-xr-x   8 root  wheel     256 Jan 16  2025 openldap
drwxr-xr-x  27 root  wheel     864 Jan 16  2025 pam.d
-rw-r--r--   1 root  wheel    9050 Jan 16  2025 passwd
-rw-r--r--   1 root  wheel      75 Jan 16  2025 paths
drwxr-xr-x   5 root  wheel     160 May  8 12:49 paths.d
drwxr-xr-x   3 root  wheel      96 Jan 16  2025 pf.anchors
-rw-r--r--   1 root  wheel    1027 Jan 16  2025 pf.conf
-rw-r--r--   1 root  wheel   28311 Jan 16  2025 pf.os
drwxr-xr-x  23 root  wheel     736 Jan 16  2025 postfix
drwxr-xr-x   2 root  wheel      64 Jan 16  2025 ppp
-r--r--r--   1 root  wheel     189 Jan 16  2025 profile
-rw-r--r--   1 root  wheel    6393 Jan 16  2025 protocols
drwxr-xr-x   4 root  wheel     128 Jan 16  2025 racoon
-rw-r--r--   1 root  wheel    1560 Jan 16  2025 rc.common
-rw-r--r--   1 root  wheel    5264 Jan 16  2025 rc.netboot
lrwxr-xr-x   1 root  wheel      22 Jan 16  2025 resolv.conf -> ../var/run/resolv.conf
-rw-r--r--   1 root  wheel       0 Jan 16  2025 rmtab
-rw-r--r--   1 root  wheel    1735 Jan 16  2025 rpc
-rw-r--r--   1 root  wheel     891 Jan 16  2025 rtadvd.conf
drwxr-xr-x   7 root  wheel     224 Jan 16  2025 security
-rw-r--r--   1 root  wheel  678260 Jan 16  2025 services
-rw-r--r--   1 root  wheel     189 Jan 16  2025 shells
drwxr-xr-x   4 root  wheel     128 Jan 16  2025 snmp
drwxr-xr-x   5 root  wheel     160 Feb  9  2025 ssh
drwxr-xr-x   6 root  wheel     192 Jan 16  2025 ssl
-r--r-----   1 root  wheel     257 Jan 16  2025 sudo_lecture
-r--r-----   1 root  wheel    1709 Jan 16  2025 sudoers
drwxr-xr-x   2 root  wheel      64 Jan 16  2025 sudoers.d
-rw-r--r--   1 root  wheel      96 Jan 16  2025 syslog.conf
-rw-r--r--   1 root  wheel    1316 Jan 16  2025 ttys
drwxr-xr-x   5 root  wheel     160 Jan 16  2025 uucp
drwxr-xr-x   6 root  wheel     192 Jan 16  2025 wfs
-rw-r--r--   1 root  wheel       0 Jan 16  2025 xtab
-r--r--r--   1 root  wheel     255 Jan 16  2025 zprofile
-r--r--r--   1 root  wheel    3094 Jan 16  2025 zshrc
-rw-r--r--   1 root  wheel    9335 Jan 16  2025 zshrc_Apple_Terminal
```

### Каталог /home
```
➜  /etc cd /home
➜  /home ls -la
total 2
dr-xr-xr-x   2 root  wheel    1 Jun  6 18:22 .
drwxr-xr-x@ 21 root  wheel  672 Feb  9  2025 ..
```

```
➜  /home ls -la /Users
total 0
drwxr-xr-x   5 root     admin   160 Feb  9  2025 .
drwxr-xr-x  22 root     wheel   704 Jan 16  2025 ..
-rw-r--r--   1 root     wheel     0 Jan 16  2025 .localized
drwxrwxrwt   8 root     wheel   256 Jan 18 16:23 Shared
drwxr-xr-x+ 57 emmaloj  staff  1824 Jun 24 21:28 emmaloj
```


## Завдання 2. Файли, каталоги та посилання

```
➜  /home cd ~
➜  ~ mkdir lab2
➜  ~ cd lab2
➜  lab2 > file.txt
➜  lab2 ls -la
total 0
drwxr-xr-x   3 emmaloj  staff    96 Jun 24 21:33 .
drwxr-xr-x+ 58 emmaloj  staff  1856 Jun 24 21:33 ..
-rw-r--r--   1 emmaloj  staff     0 Jun 24 21:33 file.txt

➜  lab2 cp file.txt file_copy.txt
➜  lab2 ls -la
total 0
drwxr-xr-x   4 emmaloj  staff   128 Jun 24 21:34 .
drwxr-xr-x+ 58 emmaloj  staff  1856 Jun 24 21:34 ..
-rw-r--r--   1 emmaloj  staff     0 Jun 24 21:33 file.txt
-rw-r--r--   1 emmaloj  staff     0 Jun 24 21:34 file_copy.txt

➜  lab2 mv file_copy.txt file_renamed.txt
➜  lab2 ls -la
total 0
drwxr-xr-x   4 emmaloj  staff   128 Jun 24 21:34 .
drwxr-xr-x+ 58 emmaloj  staff  1856 Jun 24 21:34 ..
-rw-r--r--   1 emmaloj  staff     0 Jun 24 21:33 file.txt
-rw-r--r--   1 emmaloj  staff     0 Jun 24 21:34 file_renamed.txt

➜  lab2 ln file.txt file_hardlink.txt
➜  lab2 ls -la
total 0
drwxr-xr-x   5 emmaloj  staff   160 Jun 24 21:35 .
drwxr-xr-x+ 58 emmaloj  staff  1856 Jun 24 21:35 ..
-rw-r--r--   2 emmaloj  staff     0 Jun 24 21:33 file.txt
-rw-r--r--   2 emmaloj  staff     0 Jun 24 21:33 file_hardlink.txt
-rw-r--r--   1 emmaloj  staff     0 Jun 24 21:34 file_renamed.txt

➜  lab2 ln -s file.txt file_symlink.txt
➜  lab2 ls -la
total 0
drwxr-xr-x   6 emmaloj  staff   192 Jun 24 21:35 .
drwxr-xr-x+ 58 emmaloj  staff  1856 Jun 24 21:35 ..
-rw-r--r--   2 emmaloj  staff     0 Jun 24 21:33 file.txt
-rw-r--r--   2 emmaloj  staff     0 Jun 24 21:33 file_hardlink.txt
-rw-r--r--   1 emmaloj  staff     0 Jun 24 21:34 file_renamed.txt
lrwxr-xr-x   1 emmaloj  staff     8 Jun 24 21:35 file_symlink.txt -> file.txt

➜  lab2 find ~ -name "file.txt"
/Users/emmaloj/lab2/file.txt
```

## Завдання 3. Права доступу

```
➜  lab2 ls -la file.txt
-rw-r--r--  2 emmaloj  staff  0 Jun 24 21:33 file.txt

➜  lab2 chmod 444 file.txt
➜  lab2 ls -la file.txt
-r--r--r--  2 emmaloj  staff  0 Jun 24 21:33 file.txt

➜  lab2 chmod u+w file.txt
➜  lab2 ls -la file.txt
-rw-r--r--  2 emmaloj  staff  0 Jun 24 21:33 file.txt

➜  lab2 umask
022

➜  lab2 umask 027
➜  lab2 umask
027
```

## Завдання 4. Користувачі
```
➜  lab2 sudo sysadminctl -addUser trainee -password TempPass123
2026-06-24 21:49:30.218 sysadminctl[24957:6712781] ----------------------------
2026-06-24 21:49:30.218 sysadminctl[24957:6712781] No clear text password or interactive option was specified (adduser, change/reset password will not allow user to use FDE) !
2026-06-24 21:49:30.218 sysadminctl[24957:6712781] ----------------------------
2026-06-24 21:49:30.485 sysadminctl[24957:6712781] Creating user record…
2026-06-24 21:49:31.118 sysadminctl[24957:6712781] Assigning UID: 502 GID: 20
2026-06-24 21:49:31.979 sysadminctl[24957:6712781] Creating home directory at /Users/trainee

➜  lab2 sudo dscl . -append /Groups/admin GroupMembership trainee

➜  lab2 dscl . -read /Users/trainee UniqueID PrimaryGroupID NFSHomeDirectory UserShell
NFSHomeDirectory: /Users/trainee
PrimaryGroupID: 20
UniqueID: 502
UserShell: /bin/zsh

➜  lab2 dscl . -read /Groups/admin GroupMembership
GroupMembership: root emmaloj trainee
```

### Спостереження
На macOS немає команд useradd чи usermod, як у "класичному" Linux. Натомість користувачі керуються через sysadminctl (створення) та dscl (перегляд і редагування атрибутів, у тому числі членства в групах). Аналог "sudo-групи" на macOS — це група admin, а не sudo. Дані про користувача зберігаються не у звичайному текстовому файлі /etc/passwd, а в системі Directory Service, тому й переглядаються через dscl, а не через cat /etc/passwd.
