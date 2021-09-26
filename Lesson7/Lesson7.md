# 1. Подключить репозиторий с nginx любым удобным способом,
установить nginx и потом удалить nginx, используя утилиту dpkg.

```python
george@george:~/Рабочий стол/LinuxLearning/Lesson8$ sudo apt-add-repository ppa:nginx/stable'
```

 This PPA contains the latest Stable Release version of the nginx web server software.

**Only Non-End-of-Life Ubuntu Releases are supported in this PPA**

**Development releases of Ubuntu are not officially supported by this PPA,
and uploads for those will not be available until actual final releases for those versions**
 Больше информации: https://launchpad.net/~nginx/+archive/ubuntu/stable
Нажмите [ENTER] для продолжения или Ctrl-C, чтобы отменить добавление.

Пол:1 http://dl.google.com/linux/chrome/deb stable InRelease [1 811 B]
Пол:2 http://dl.google.com/linux/chrome/deb stable/main amd64 Packages [1 096 B]
Сущ:3 http://ru.archive.ubuntu.com/ubuntu focal InRelease                                                           
Пол:4 http://ru.archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]                                          
Пол:5 http://ppa.launchpad.net/nginx/stable/ubuntu focal InRelease [17,5 kB]                                        
Пол:6 http://ru.archive.ubuntu.com/ubuntu focal-backports InRelease [101 kB]                                        
Пол:7 http://security.ubuntu.com/ubuntu focal-security InRelease [114 kB]                                           
Пол:8 http://ru.archive.ubuntu.com/ubuntu focal-updates/main i386 Packages [538 kB]                                 
Пол:9 http://ppa.launchpad.net/nginx/stable/ubuntu focal/main i386 Packages [1 224 B]                               
Пол:10 http://ppa.launchpad.net/nginx/stable/ubuntu focal/main amd64 Packages [4 944 B]                             
Пол:11 http://ru.archive.ubuntu.com/ubuntu focal-updates/main amd64 Packages [1 221 kB]                             
Пол:12 http://ppa.launchpad.net/nginx/stable/ubuntu focal/main Translation-en [4 572 B]                             
Пол:13 http://security.ubuntu.com/ubuntu focal-security/main amd64 DEP-11 Metadata [27,6 kB]                        
Пол:14 http://ru.archive.ubuntu.com/ubuntu focal-updates/main amd64 DEP-11 Metadata [283 kB]                        
Пол:15 http://security.ubuntu.com/ubuntu focal-security/universe amd64 DEP-11 Metadata [61,1 kB]                    
Пол:16 http://ru.archive.ubuntu.com/ubuntu focal-updates/main amd64 c-n-f Metadata [14,3 kB]                        
Пол:17 http://ru.archive.ubuntu.com/ubuntu focal-updates/universe amd64 Packages [855 kB]                           
Пол:18 http://security.ubuntu.com/ubuntu focal-security/multiverse amd64 DEP-11 Metadata [2 464 B]             
Пол:19 http://ru.archive.ubuntu.com/ubuntu focal-updates/universe i386 Packages [634 kB]                            
Пол:20 http://ru.archive.ubuntu.com/ubuntu focal-updates/universe amd64 DEP-11 Metadata [354 kB]                    
Пол:21 http://ru.archive.ubuntu.com/ubuntu focal-updates/multiverse amd64 DEP-11 Metadata [944 B]                   
Пол:22 http://ru.archive.ubuntu.com/ubuntu focal-backports/universe amd64 DEP-11 Metadata [10,4 kB]                 
Получено 4 361 kB за 12с (371 kB/s)                                                                                 
Чтение списков пакетов… Готово

```jpython
cat /etc/apt/sources.list.d/nginx-ubuntu-stable-focal.list
```

deb http://ppa.launchpad.net/nginx/stable/ubuntu focal main
# deb-src http://ppa.launchpad.net/nginx/stable/ubuntu focal main

```python
george@george:~$ sudo apt install nginx -y

sudo dpkg -r nginx
```

# 2. Установить пакет на свой выбор, используя snap.

```python
sudo snap find telegram
sudo snap install telegram-desktop
```
