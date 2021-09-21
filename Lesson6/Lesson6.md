### 1. Написать скрипт, который удаляет из текстового файла пустые строки и заменяет маленькие символы на большие. Воспользуйтесь tr или SED.

george@george:~/Рабочий стол/LinuxLearning/Lesson6/Task2$ cat example.txt
first summer

Linux editor


compilator 

throw


sed '/^$/d' example.txt
sed -i 's/[a-z]/\U&/g' example.txt

george@george:~/Рабочий стол/LinuxLearning/Lesson6/Task2$ cat example.txt 
FIRST SUMMER
LINUX EDITOR
COMPILATOR 
THROW

### 2. Создать однострочный скрипт, который создаст директории для нескольких годов (2010–2017), в них — поддиректории для месяцев (от 01 до 12), и в каждый из них запишет несколько файлов с произвольными записями. Например, 001.txt, содержащий текст «Файл 001», 002.txt с текстом «Файл 002» и т. д.

for i in Ex2/{2010..2017}/{01..12}; do mkdir -p $i; for j in {001..005}; do echo "Файл $j" > $i/$j.txt; done; done


