# Домашнє завдання №5. Мережа, SSH, передача файлів
Лой Еммануель Ігорівна

## Завдання 1. Мережева діагностика

```
➜  ~ ifconfig
en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	ether 0e:9d:97:xx:xx:xx
	inet 192.168.2.15 netmask 0xffffff00 broadcast 192.168.2.255
	media: autoselect
	status: active
```
Локальна IP-адреса інтерфейсу en0 (Wi-Fi) — 192.168.2.15.

```
➜  ~ ping -c 5 8.8.8.8
PING 8.8.8.8 (8.8.8.8): 56 data bytes
64 bytes from 8.8.8.8: icmp_seq=0 ttl=118 time=18.721 ms
64 bytes from 8.8.8.8: icmp_seq=1 ttl=118 time=21.461 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=118 time=17.005 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=118 time=11.035 ms
64 bytes from 8.8.8.8: icmp_seq=4 ttl=118 time=9.865 ms

--- 8.8.8.8 ping statistics ---
5 packets transmitted, 5 packets received, 0.0% packet loss
round-trip min/avg/max/stddev = 9.865/15.617/21.461/4.468 ms
```
Доступ до інтернету є, втрат пакетів немає (0.0% packet loss)

```
➜  ~ lsof -i -P | grep LISTEN
rapportd    609 emmaloj    8u  IPv4 0xa45e3f6af4dff3f5      0t0  TCP *:64458 (LISTEN)
rapportd    609 emmaloj    9u  IPv6 0x9c8d490b2ce6ad35      0t0  TCP *:64458 (LISTEN)
ControlCe   644 emmaloj    8u  IPv4 0x41f25092c9e370c2      0t0  TCP *:7000 (LISTEN)
ControlCe   644 emmaloj    9u  IPv6 0x138f442bf6a33396      0t0  TCP *:7000 (LISTEN)
ControlCe   644 emmaloj   10u  IPv4 0x20491876f3681262      0t0  TCP *:5000 (LISTEN)
ControlCe   644 emmaloj   11u  IPv6 0xf227dc834ec1f865      0t0  TCP *:5000 (LISTEN)
Code\x20H   931 emmaloj   48u  IPv4  0x901e775c8d6fd21      0t0  TCP *:5500 (LISTEN)
Postman    1080 emmaloj   36u  IPv4 0x4e982487745182dc      0t0  TCP localhost:10533 (LISTEN)
postgres   5438 emmaloj    7u  IPv6 0xf3ff45ac232c7433      0t0  TCP localhost:5432 (LISTEN)
postgres   5438 emmaloj    8u  IPv4 0xf780bb067cc4c42d      0t0  TCP localhost:5432 (LISTEN)
mysqld    15324 emmaloj   19u  IPv4 0xfb8d0071f0be092f      0t0  TCP localhost:33060 (LISTEN)
mysqld    15324 emmaloj   22u  IPv4 0x13fcb82b36984f77      0t0  TCP localhost:3306 (LISTEN)
dbeaver   16239 emmaloj  115u  IPv6 0x4a353c1383f84788      0t0  TCP localhost:62044 (LISTEN)
node      95491 emmaloj   17u  IPv6 0x947e3fca3c3f2999      0t0  TCP *:3000 (LISTEN)
```
Приклади сервісів, що слухають порти:
база даних PostgreSQL на порту 5432
база даних MySQL на порту 3306
Node.js на порту 3000

## Notes
Оскільки на macOS немає команд ip і ss, використала замість них ifconfig та lsof -i -P


## Завдання 2. SSH-доступ з ключами та config
```
➜  ~ ls -la ~/.ssh
total 40
drwx------   7 emmaloj  staff   224 Oct 16  2024 .
drwxr-xr-x+ 59 emmaloj  staff  1888 Jun 28 17:09 ..
-rw-------   1 emmaloj  staff   432 Oct 16  2024 id_ed25519
-rw-r--r--   1 emmaloj  staff   116 Oct 16  2024 id_ed25519.pub
-rw-------   1 emmaloj  staff  2610 Mar  6  2022 id_rsa
-rw-r--r--   1 emmaloj  staff   580 Mar  6  2022 id_rsa.pub
-rw-r--r--   1 emmaloj  staff   734 May 22  2022 known_hosts
```

```
➜  ~ sudo systemsetup -setremotelogin on
Password:
➜  ~ sudo systemsetup -getremotelogin
Remote Login: On
```

```
➜  ~ ssh-copy-id emmaloj@localhost
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/Users/emmaloj/.ssh/id_ed25519.pub"
The authenticity of host 'localhost (::1)' can't be established.
ED25519 key fingerprint is SHA256:juX9zghXucpHeYODNb3Wz4UfGFlidKci/LXwIjU/Fbg.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
(emmaloj@localhost) Password:

Number of key(s) added:        1

Now try logging into the machine, with:   "ssh 'emmaloj@localhost'"
and check to make sure that only the key(s) you wanted were added.
```

```
➜  ~ cat ~/.ssh/config
Host myserver
    HostName localhost
    User emmaloj
    IdentityFile ~/.ssh/id_ed25519
```

```
➜  ~ ssh myserver
Last login: Sun Jun 28 16:54:36 2026
➜  ~ exit
Connection to localhost closed.
```

Ім'я Host у config - myserver
підключення пройшло без пароля 

## Notes
Для практики SSH використала localhost, для цього увімкнула Remote Login через systemsetup
SSH-ключі нові не генерувала, оскільки вони вже були створені

## Завдання 3. Копіювання файлів між машинами

```
➜  ~ echo "test" > test.txt
➜  ~ cat test.txt
test

➜  ~ scp test.txt myserver:~/test_remote.txt
test.txt                                      100%    5     4.5KB/s   00:00    

➜  ~ ssh myserver "cat ~/test_remote.txt"
test
```

```
➜  ~ ssh myserver "mkdir -p ~/sync_folder"
```

```
➜  ~ mkdir -p ~/local_sync_test
➜  ~ echo "file 1" > ~/local_sync_test/file1.txt
➜  ~ echo "file 2" > ~/local_sync_test/file2.txt

➜  ~ rsync -avz ~/local_sync_test/ myserver:~/sync_folder/
building file list ... done
./
file1.txt
file2.txt

sent 215 bytes  received 70 bytes  570.00 bytes/sec
total size is 14  speedup is 0.05

➜  ~ ssh myserver "ls -la ~/sync_folder"
total 16
drwxr-xr-x   4 emmaloj  staff   128 Jun 28 17:30 .
drwxr-xr-x+ 63 emmaloj  staff  2016 Jun 28 17:31 ..
-rw-r--r--   1 emmaloj  staff     7 Jun 28 17:30 file1.txt
-rw-r--r--   1 emmaloj  staff     7 Jun 28 17:30 file2.txt
```

```
➜  ~ sftp myserver
Connected to myserver.
sftp> ls sync_folder
sync_folder/file1.txt     sync_folder/file2.txt     
sftp> exit
➜  ~ 
```

Шлях до файлів на сервері: ~/sync_folder/ (/Users/emmaloj/sync_folder/).
Для перевірки використала: 
ssh myserver "cat" (вміст файлу) 
ssh myserver "ls -la" (список файлів) 
sftp myserver з командою ls sync_folder

