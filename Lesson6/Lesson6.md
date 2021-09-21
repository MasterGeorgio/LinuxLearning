### 1. Написать скрипт, который удаляет из текстового файла пустые строки и заменяет маленькие символы на большие.
#Воспользуйтесь tr или SED.

george@george:~/Рабочий стол/LinuxLearning/Lesson6/Task2$ cat example.txt
first summer

Linux editor


compilator 

throw

#Results
sed '/^$/d' example.txt
sed -i 's/[a-z]/\U&/g' example.txt

george@george:~/Рабочий стол/LinuxLearning/Lesson6/Task2$ cat example.txt 
FIRST SUMMER
LINUX EDITOR
COMPILATOR 
THROW

#-------------------------------------------------------------------------------------------------------------------

# 2. Создать однострочный скрипт, который создаст директории для нескольких годов (2010–2017),
#в них — поддиректории для месяцев (от 01 до 12), и в каждый из них запишет несколько файлов с произвольными записями.
#Например, 001.txt, содержащий текст «Файл 001», 002.txt с текстом «Файл 002» и т. д.

#Command:
for i in Ex2/{2010..2017}/{01..12}; do mkdir -p $i; for j in {001..005}; do echo "Файл $j" > $i/$j.txt; done; done

#Results:
george@george:~/Рабочий стол/LinuxLearning/Lesson6$ for i in Ex2/{2010..2017}/{01..12}; do mkdir -p $i; for j in {001..005}; do echo "Файл $j" > $i/$j.txt; done; done
george@george:~/Рабочий стол/LinuxLearning/Lesson6$ ls -l Ex2/
итого 32
drwxrwxr-x 14 george george 4096 сен 21 23:21 2010
drwxrwxr-x 14 george george 4096 сен 21 23:21 2011
drwxrwxr-x 14 george george 4096 сен 21 23:21 2012
drwxrwxr-x 14 george george 4096 сен 21 23:21 2013
drwxrwxr-x 14 george george 4096 сен 21 23:21 2014
drwxrwxr-x 14 george george 4096 сен 21 23:21 2015
drwxrwxr-x 14 george george 4096 сен 21 23:21 2016
drwxrwxr-x 14 george george 4096 сен 21 23:21 2017
george@george:~/Рабочий стол/LinuxLearning/Lesson6$ ls -l Ex2/2017/
итого 48
drwxrwxr-x 2 george george 4096 сен 21 23:21 01
drwxrwxr-x 2 george george 4096 сен 21 23:21 02
drwxrwxr-x 2 george george 4096 сен 21 23:21 03
drwxrwxr-x 2 george george 4096 сен 21 23:21 04
drwxrwxr-x 2 george george 4096 сен 21 23:21 05
drwxrwxr-x 2 george george 4096 сен 21 23:21 06
drwxrwxr-x 2 george george 4096 сен 21 23:21 07
drwxrwxr-x 2 george george 4096 сен 21 23:21 08
drwxrwxr-x 2 george george 4096 сен 21 23:21 09
drwxrwxr-x 2 george george 4096 сен 21 23:21 10
drwxrwxr-x 2 george george 4096 сен 21 23:21 11
drwxrwxr-x 2 george george 4096 сен 21 23:21 12
george@george:~/Рабочий стол/LinuxLearning/Lesson6$ ls -l Ex2/2017/0
01/ 02/ 03/ 04/ 05/ 06/ 07/ 08/ 09/ 
george@george:~/Рабочий стол/LinuxLearning/Lesson6$ ls -l Ex2/2017/11
итого 20
-rw-rw-r-- 1 george george 13 сен 21 23:22 001.txt
-rw-rw-r-- 1 george george 13 сен 21 23:22 002.txt
-rw-rw-r-- 1 george george 13 сен 21 23:22 003.txt
-rw-rw-r-- 1 george george 13 сен 21 23:22 004.txt
-rw-rw-r-- 1 george george 13 сен 21 23:22 005.txt

#-------------------------------------------------------------------------------------------------------------------

# 3. Использовать команду AWK на вывод длинного списка каталога, чтобы отобразить только права доступа к файлам.
# Затем отправить в конвейере этот вывод на sort и uniq, чтобы отфильтровать все повторяющиеся строки.
#Command

ls -l | mawk ' {print $1} ' | sort | uniq

#Results:
george@george:/$ ls -l
итого 2097240
lrwxrwxrwx   1 root root          7 июл 11 17:05 bin -> usr/bin
drwxr-xr-x   4 root root       4096 сен 20 19:30 boot
drwxrwxr-x   2 root root       4096 июл 11 17:07 cdrom
drwxr-xr-x  20 root root       4280 сен 21 22:19 dev
drwxr-xr-x 130 root root      12288 сен 20 19:30 etc
drwxr-xr-x   7 root root       4096 сен  9 23:48 home
lrwxrwxrwx   1 root root          7 июл 11 17:05 lib -> usr/lib
lrwxrwxrwx   1 root root          9 июл 11 17:05 lib32 -> usr/lib32
lrwxrwxrwx   1 root root          9 июл 11 17:05 lib64 -> usr/lib64
lrwxrwxrwx   1 root root         10 июл 11 17:05 libx32 -> usr/libx32
drwx------   2 root root      16384 июл 11 17:04 lost+found
drwxr-xr-x   4 root root       4096 июл 26 20:39 media
drwxr-xr-x   2 root root       4096 фев  9  2021 mnt
drwxr-xr-x   5 root root       4096 сен  2 21:15 opt
dr-xr-xr-x 347 root root          0 сен 21 22:19 proc
drwx------   5 root root       4096 сен  2 23:29 root
drwxr-xr-x  34 root root        940 сен 21 22:20 run
lrwxrwxrwx   1 root root          8 июл 11 17:05 sbin -> usr/sbin
drwxr-xr-x  15 root root       4096 сен 20 19:40 snap
drwxr-xr-x   2 root root       4096 фев  9  2021 srv
-rw-------   1 root root 2147483648 июл 11 17:04 swapfile
dr-xr-xr-x  13 root root          0 сен 21 22:19 sys
drwxrwxrwt  21 root root      12288 сен 21 23:19 tmp
drwxr-xr-x  14 root root       4096 фев  9  2021 usr
drwxr-xr-x  15 root root       4096 сен 10 00:08 var

george@george:/$ ls -l | mawk ' {print $1} ' | sort | uniq
drwx------
drwxrwxrwt
drwxrwxr-x
drwxr-xr-x
dr-xr-xr-x
lrwxrwxrwx
-rw-------
итого


