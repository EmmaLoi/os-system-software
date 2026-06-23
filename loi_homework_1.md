# Домашнє завдання №1. Основи Linux і робота в терміналі
Лой Еммануель Ігорівна

## Завдання 1. Базові команди

### 1. Вміст домашнього каталогу
```
➜  ~ pwd
/Users/emmaloj
➜  ~ ls -la
total 776
drwxr-xr-x+  55 emmaloj  staff    1760 Jun 23 17:55 .
drwxr-xr-x    5 root     admin     160 Feb  9  2025 ..
-r--------    1 emmaloj  staff       8 Dec 10  2021 .CFUserTextEncoding
-rw-r--r--@   1 emmaloj  staff   12292 Jun 22 22:00 .DS_Store
drwx------   79 emmaloj  staff    2528 Jun 22 22:00 .Trash
drwxr-xr-x    3 emmaloj  staff      96 Jun  9 19:39 .android
-rw-r--r--    1 emmaloj  staff     183 Dec 27  2021 .bash_profile
drwxr-xr-x    4 emmaloj  staff     128 May 16 14:15 .cache
drwxr-xr-x    3 emmaloj  staff      96 Mar  7  2022 .cocoapods
drwx------@   3 emmaloj  staff      96 May  8 13:42 .copilot
-rw-r--r--    1 emmaloj  staff      57 Mar  7  2022 .gitconfig
drwxr-xr-x    8 emmaloj  staff     256 Jun  9 19:39 .gradle
drwxr-xr-x    3 emmaloj  staff      96 Apr 10  2023 .groovy
drwxr-xr-x    3 emmaloj  staff      96 Mar  9  2023 .hawtjni
drwxr-xr-x    3 emmaloj  staff      96 Oct 16  2024 .idlerc
drwxr-xr-x   37 emmaloj  staff    1184 Jan 13  2024 .jenkins
drwxr-xr-x    4 emmaloj  staff     128 Jun 11 20:13 .m2
drwxr-xr-x@   7 emmaloj  staff     224 Jun  7 23:20 .npm
drwxr-xr-x    2 emmaloj  staff      64 May  8 11:46 .nvm
drwxr-xr-x   22 emmaloj  staff     704 May 16 21:01 .oh-my-zsh
drwxr-xr-x    3 emmaloj  staff      96 Dec 15  2021 .oracle_jre_usage
drwxr-xr-x@   6 emmaloj  staff     192 May 16 21:41 .rest-client
drwxr-xr-x   11 emmaloj  staff     352 Jun  8 20:30 .sdkman
drwx------    7 emmaloj  staff     224 Oct 16  2024 .ssh
drwxr-xr-x    4 emmaloj  staff     128 Mar  6  2022 .swiftpm
-rw-------    1 emmaloj  staff    1486 Oct 19  2022 .viminfo
drwxr-xr-x@   5 emmaloj  staff     160 May  8 13:42 .vscode
drwxr-xr-x@   3 emmaloj  staff      96 May  8 13:42 .vscode-shared
-rw-r--r--    1 emmaloj  staff   48117 Jan  5  2023 .zcompdump-MacBook Air — Эмма-5.8
-rw-r--r--@   1 emmaloj  staff   49810 May 16 21:01 .zcompdump-MacBook Air — Эмма-5.9
-rw-r--r--    1 emmaloj  staff   49697 Jun 21 20:59 .zcompdump-MacBook-Air-Emma-5.9
-rw-r--r--@   1 emmaloj  staff   15920 May 18 19:24 .zcompdump-MacBook-Air-Emma-5.9.MacBook-Air-Emma.local.99972
-r--r--r--    1 emmaloj  staff  117488 Jun 21 20:59 .zcompdump-MacBook-Air-Emma-5.9.zwc
-rw-r--r--    1 emmaloj  staff     208 Oct 16  2024 .zprofile
-rw-r--r--    1 emmaloj  staff      42 Dec 15  2021 .zprofile.pysave
-rw-------@   1 emmaloj  staff   42064 Jun 23 17:55 .zsh_history
drwx------    4 emmaloj  staff     128 Jun 21 20:59 .zsh_sessions
-rw-r--r--    1 emmaloj  staff    4049 Dec 27  2021 .zshrc
drwx------@   4 emmaloj  staff     128 Oct 17  2024 Applications
drwxr-xr-x@   3 emmaloj  staff      96 Jun 21 20:57 Applications (Parallels)
drwx------@   6 emmaloj  staff     192 Jan 18 16:45 Desktop
drwx------@  80 emmaloj  staff    2560 Jun 22 22:00 Documents
drwx------@ 407 emmaloj  staff   13024 Jun 22 22:00 Downloads
drwxr-xr-x    9 emmaloj  staff     288 Oct  6  2022 IdeaProjects
drwx------@ 105 emmaloj  staff    3360 Jun 21 21:42 Library
drwx------@   6 emmaloj  staff     192 Jan 23 00:24 Movies
drwx------@   5 emmaloj  staff     160 Jan 18 16:45 Music
drwx------@   2 emmaloj  staff      64 Jun 21 20:57 Parallels
drwx------@   5 emmaloj  staff     160 Jan 18 16:45 Pictures
drwxr-xr-x    3 emmaloj  staff      96 Mar  3  2022 Postman
drwxr-xr-x    3 emmaloj  staff      96 Mar  3  2022 Postman Agent
drwxr-xr-x+   4 emmaloj  staff     128 Dec 10  2021 Public
drwxr-xr-x    5 emmaloj  staff     160 Oct 24  2024 PycharmProjects
drwxr-xr-x    8 emmaloj  staff     256 May  8 15:50 file-organizer
-rw-r--r--@   1 emmaloj  staff   12433 May  8 15:50 file-organizer.zip
```

```
➜  ~ cd Downloads
ls -la
total 48952872
drwxr-xr-x@   3 emmaloj  staff          96 Jan 18 16:46 $RECYCLE.BIN
drwx------@ 407 emmaloj  staff       13024 Jun 22 22:00 .
drwxr-xr-x+  55 emmaloj  staff        1760 Jun 23 17:56 ..
-rw-r--r--@   1 emmaloj  staff       16388 Jun 22 22:00 .DS_Store
-rw-r--r--    1 emmaloj  staff           0 Dec 10  2021 .localized
-rw-r--r--@   1 emmaloj  staff     1340961 May 28 15:16 1 - SDLC Documentation.pdf
-rw-r--r--@   1 emmaloj  staff      109663 Feb  1 16:38 10_Основи математичної статистики_лекція.docx
-rw-r--r--@   1 emmaloj  staff     1775228 Jun 18 18:35 11 - Prototyping.pdf
-rw-r--r--@   1 emmaloj  staff       45021 Feb  1 16:38 12_Метод моментів_довірчі інтервали_лекція.docx
-rw-r--r--@   1 emmaloj  staff      219053 Feb  1 16:38 14_Перевірка статистичних гіпотез_лекція.docx
-rw-r--r--@   1 emmaloj  staff      831986 Jan 31 21:16 3_Основні поняття. Класифікація подій_лекція.docx
-rw-r--r--@   1 emmaloj  staff     5188985 Aug 28  2025 4. Дослідження ринку, споживача, конкурентів.pdf
-rw-r--r--@   1 emmaloj  staff      711254 Jan 31 21:17 4_Ймовірність події. Властивості_лекція.docx
-rw-r--r--@   1 emmaloj  staff     5565325 Aug 28  2025 5. Business Model.pdf
-rw-r--r--@   1 emmaloj  staff      125705 Dec 25  2024 5431488562932608321.pdf
-rw-r--r--@   1 emmaloj  staff     7562982 Aug 28  2025 6. Finance in IT.pdf
-rw-r--r--@   1 emmaloj  staff       30924 Jan 31 21:18 6_Повна ймовірність_Байєс_Бернуллі_лекція.docx
-rw-r--r--@   1 emmaloj  staff     5154400 Aug 28  2025 7. Воронка AARRRR.pdf
-rw-r--r--@   1 emmaloj  staff     3064761 Jun 20 19:02 8919ff5a-de59-44aa-a6e3-843fc652a272image (1).png
-rw-r--r--@   1 emmaloj  staff     3064761 Jun 20 18:51 8919ff5a-de59-44aa-a6e3-843fc652a272image.png
-rw-r--r--@   1 emmaloj  staff      720480 Jan 31 21:21 8_Дискретні випадкові величини_лекція.docx
-rw-r--r--@   1 emmaloj  staff        8127 May 29 20:31 HW1_Аналіз_кіберінциденту.docx
-rw-r--r--@   1 emmaloj  staff     1028516 May  6 15:15 HW2_Loi.ipynb
-rw-r--r--@   1 emmaloj  staff       24414 May  6 15:39 HW3_Loi.ipynb
-rw-r--r--@   1 emmaloj  staff      407615 May  6 16:07 HW4_Loi.ipynb
-rw-r--r--@   1 emmaloj  staff       17099 May  6 16:54 HW5_Loi.ipynb
-rw-r--r--@   1 emmaloj  staff      136222 May  6 17:18 HW6_Loi.ipynb
-rw-r--r--@   1 emmaloj  staff       73227 May  7 17:00 HW7_Loi.ipynb
-rw-r--r--@   1 emmaloj  staff       13600 May  7 17:53 HW8_Loi.ipynb
-rw-r--r--@   1 emmaloj  staff       13997 May  7 18:27 HW9_Loi.ipynb
-rw-r--r--@   1 emmaloj  staff        8941 Jun  6 14:57 Header.png
-rw-r--r--@   1 emmaloj  staff       15336 Jun  6 15:00 Header.svg
-rw-r--r--@   1 emmaloj  staff     5478953 Jun  6 14:46 Home • Desktop.png
-rw-r--r--@   1 emmaloj  staff       27836 Jan 17 20:24 Homework _Software requirements testing_(Loi Emmanuel).xlsx
-rw-r--r--@   1 emmaloj  staff      131601 Nov  7  2024 Phrase_bank._Making_small_talk.pdf
-rw-r--r--@   1 emmaloj  staff      169142 Jan 20  2025 Phrase_bank._Making_suggestions__1_.pdf
-rw-r--r--@   1 emmaloj  staff      572225 Jan 31 21:13 Тема 1. Комбінаторика - конспект.docx
-rw-r--r--@   1 emmaloj  staff     2349418 Nov 26  2024 Тема 5_РС_Заняття 4.pptx.pdf
-rw-r--r--@   1 emmaloj  staff       76846 Sep 24  2025 Шаблон про визнання попередніх результатів навчання .pdf
-rw-r--r--@   1 emmaloj  staff      599358 Sep 25  2025 Шаблон_про_визнання_попередніх_результатів_навчання_.pdf
➜  Downloads 
```

### 3. Створення порожнього файлу (без touch)

```
$ > myfile.txt
$ ls -la myfile.txt
-rw-r--r--  1 emmaloj  staff  1 Jun 23 18:05 myfile.txt
```

### 4. Перегляд вмісту файлу

```
➜  Downloads cat myfile.txt

➜  Downloads 
```


### 5. Перехід у домашній каталог абсолютним шляхом

```
➜  Downloads cd /Users/emmaloj
pwd
/Users/emmaloj 
```

### 6. Перехід у домашній каталог відносним шляхом

```
➜  ~ cd Downloads
➜  Downloads pwd
/Users/emmaloj/Downloads
➜  Downloads cd ..
➜  ~ pwd
/Users/emmaloj
```



## Завдання 2. Робота з документацією

### Виконані команди

```
➜  ~ man ls
➜  ~ help cd
zsh: command not found: help

➜  ~ bash
bash-3.2$ help cd
cd: cd [-L|-P] [dir]
    Change the current directory to DIR.  The variable $HOME is the
    default DIR.  The variable CDPATH defines the search path for
    the directory containing DIR.  Alternative directory names in CDPATH
    are separated by a colon (:).  A null directory name is the same as
    the current directory, i.e. `.'.  If DIR begins with a slash (/),
    then CDPATH is not used.  If the directory is not found, and the
    shell option `cdable_vars' is set, then try the word as a variable
    name.  If that variable has a value, then cd to the value of that
    variable.  The -P option says to use the physical directory structure
    instead of following symbolic links; the -L option forces symbolic links
    to be followed.
bash-3.2$ exit

➜  ~ man cat
Unknown locale, assuming C
➜  ~ man man
Unknown locale, assuming C
➜  ~ cp --help
cp: illegal option -- -
usage: cp [-R [-H | -L | -P]] [-fi | -n] [-aclpSsvXx] source_file target_file
       cp [-R [-H | -L | -P]] [-fi | -n] [-aclpSsvXx] source_file ... target_directory
➜  ~ mv --help
mv: illegal option -- -
usage: mv [-f | -i | -n] [-hv] source target
       mv [-f | -i | -n] [-v] source ... directory
```

### Відповіді на питання

1. Який ключ ls показує приховані файли?
Ключ -a (від "all") - показує всі файли, включно з прихованими (ті, що починаються з крапки, наприклад .bashrc, .gitconfig).

2. Який ключ у cat нумерує рядки?
Ключ -n - виводить вміст файлу з номерами рядків зліва.

3. Чим відрізняються man і --help?
man - це повна сторінка документації з детальним описом, прикладами і всіма опціями команди, відкривається в окремому режимі для читання.
--help (або help для вбудованих команд оболонки) - коротка довідка прямо в терміналі, без зайвих деталей.

### Спостереження
Помітила що у zsh команда help не працює, щоб її використати, тимчасово зайшла в bash командою bash, виконала help cd, а потім вийшла командою exit.


## Завдання 3. Міні-сценарій
```
➜  ~ cd Downloads
➜  Downloads pwd
/Users/emmaloj/Downloads
➜  Downloads > hw_test.txt
ls -la hw_test.txt
^C
➜  Downloads ls -la hw_test.txt
-rw-r--r--  1 emmaloj  staff  0 Jun 23 18:31 hw_test.txt
➜  Downloads ls -la
total 48952904
drwxr-xr-x@   3 emmaloj  staff          96 Jan 18 16:46 $RECYCLE.BIN
drwx------@ 410 emmaloj  staff       13120 Jun 23 18:31 .
drwxr-xr-x+  57 emmaloj  staff        1824 Jun 23 18:31 ..
-rw-r--r--@   1 emmaloj  staff       18436 Jun 23 18:22 .DS_Store
-rw-r--r--    1 emmaloj  staff           0 Dec 10  2021 .localized
-rw-r--r--@   1 emmaloj  staff     1340961 May 28 15:16 1 - SDLC Documentation.pdf
➜  Downloads cd ../Documents
➜  Documents pwd
/Users/emmaloj/Documents
➜  Documents cd ../Downloads
➜  Downloads pwd
/Users/emmaloj/Downloads
➜  Downloads man ls
```









