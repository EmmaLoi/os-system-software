# Домашнє завдання №6. Bash-скрипт (Варіант A — бекап логів)
Лой Еммануель Ігорівна

## Скрипт backup.sh

``` bash
#!/bin/bash

if [ "$#" -ne 2 ]; then
    echo "Usage: ./backup.sh <log_dir> <backup_dir>"
    exit 1
fi

LOG_DIR="$1"
BACKUP_DIR="$2"

if [ ! -d "$LOG_DIR" ] || [ ! -d "$BACKUP_DIR" ]; then
    echo "Usage: ./backup.sh <log_dir> <backup_dir>"
    exit 1
fi

LOCK_FILE="/tmp/backup.lock"

if [ -f "$LOCK_FILE" ]; then
    echo "Backup already running"
    exit 1
fi

touch "$LOCK_FILE"
trap 'rm -f "$LOCK_FILE"' EXIT

TIMESTAMP=$(date +"%Y-%m-%d_%H-%M")
ARCHIVE_PATH="${BACKUP_DIR}/logs_backup_${TIMESTAMP}.tar.gz"

tar -czf "$ARCHIVE_PATH" -C "$LOG_DIR" .

if [ $? -ne 0 ]; then
    echo "Backup failed"
    exit 2
fi

echo "Backup created: $ARCHIVE_PATH"
```

## Тестування з різними аргументами

### Тест 1: без аргументів

``` 
➜  ~ ~/backup.sh
Usage: ./backup.sh <log_dir> <backup_dir>

➜  ~ echo $?
1
```

### Тест 2: неіснуючий каталог
```
➜  ~ ~/backup.sh /not/a/real/path ~/test_backup
Usage: ./backup.sh <log_dir> <backup_dir>
```

### Тест 3: правильні аргументи
```
➜  ~ ~/backup.sh ~/test_logs ~/test_backup
Backup created: /Users/emmaloj/test_backup/logs_backup_2026-06-29_22-31.tar.gz

➜  ~ ls -la ~/test_backup
total 8
drwxr-xr-x   3 emmaloj  staff    96 Jun 29 22:31 .
drwxr-xr-x+ 68 emmaloj  staff  2176 Jun 29 22:31 ..
-rw-r--r--   1 emmaloj  staff   185 Jun 29 22:31 logs_backup_2026-06-29_22-31.tar.gz
```

### Тест 4: захист від паралельного запуску
```
➜  ~ touch /tmp/backup.lock
➜  ~ ~/backup.sh ~/test_logs ~/test_backup
Backup already running
```

### Тест 5: lock-файл видаляється сам після завершення
```
➜  ~ rm /tmp/backup.lock
➜  ~ ~/backup.sh ~/test_logs ~/test_backup
ls /tmp/backup.lock
Backup created: /Users/emmaloj/test_backup/logs_backup_2026-06-29_22-33.tar.gz

ls: /tmp/backup.lock: No such file or directory
```

## Notes

Скрипт бере 2 аргументи: папку з логами і папку для бекапу. Якщо щось не так з аргументами, пише Usage і вихід з кодом 1.

Скрипт перевіряє lock-файл, щоб два бекапи не запустились одночасно. Якщо є "Backup already running".

Потім архівує логи в tar.gz з датою в назві. Якщо не вийшло, то "Backup failed", код 2. Якщо вийшло, пише шлях до архіву.


