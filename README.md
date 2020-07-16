# Содержание
- [ИСР № 3](#инвариативная-самостоятельная-работа--3)
    - [1 задание]()
    - [2 задание]()
    - [3 задание]()
    - [4 задание]()
- [ВСР № 3](#вариативная-самостоятельная-работа--3)
    - [1 задание]()
    - [2 задание]()
- [ЛР № 10]()
- [ЛР № 11]()

# Инвариативная самостоятельная работа № 3
### 3.1. Создание аннотированного списка библиотек для работы с текстом в Python.
[Результат.](https://github.com/python-basic/sem3-t3-Rakleed/blob/master/src/programming-indepworkinvar3-1-result.pdf)

### [3.2. Разработка сценария с реализацией операции поиска подстроки в тексте.](https://repl.it/@Rakleed/programming-indepworkinvar3-2)
```python
"""
    Автор: Моисеенко Павел, группа № 1, подгруппа № 2.

    ИСР 3.2. Задание: разработайте сценарий с реализацией операции поиска подстроки в тексте.

"""


def main():
    search_string = input("Введите строку. ")
    what_to_find = input("Что бы вы хотели найти? ")
    all_occurrences(search_string, what_to_find)


def all_occurrences(search_string, what_to_find):
    occurrence = search_string.find(what_to_find)
    if occurrence != -1:
        print('Первое вхождение подстроки:', occurrence)
    else:
        print('Нет вхождений подстроки.')

    length_search_string = len(search_string)
    length_what_to_find = len(what_to_find)
    while occurrence != -1:
        occurrence = search_string.find(what_to_find, occurrence +
                                        length_what_to_find,
                                        length_search_string)
        if occurrence != -1:
            print('Вхождение подстроки:', occurrence)
        else:
            print('Больше вхождений нет.')


main()
```
![Result of indepworkinvar3-2](https://github.com/python-basic/sem3-t3-Rakleed/blob/master/src/programming-indepworkinvar3-2-result.png)

### [3.3. Создание скрипта для считывания данных справочных логов из текстового файла и преобразования их в CSV-формат с последующей записью в новый файл.](https://repl.it/@Rakleed/programming-indepworkinvar3-3)
```python
"""
    Автор: Моисеенко Павел, группа № 1, подгруппа № 2.

    ИСР 3.3. Задание: создайте скрипт для считывания данных справочных
    логов из текстового файла и преобразования их в CSV-формат с после-
    дующей записью в новый файл.

"""


def json_function():
    import json
    help_logs = open('file.json')
    data_list = json.load(help_logs)
    return data_list


def csv_function(data_list):
    import csv
    with open('file.csv', 'w', newline='') as csv_file_handler:
        csv_writer = csv.writer(
            csv_file_handler,
            delimiter=';',
            quotechar='"',
            quoting=csv.QUOTE_MINIMAL)
        csv_writer.writerow(list(data_list[0].keys()))
        for d_dict in data_list:
            csv_writer.writerow(list(d_dict.values()))


data = json_function()
csv_function(data)
```
![Result of indepworkinvar3-3](https://github.com/python-basic/sem3-t3-Rakleed/blob/master/src/programming-indepworkinvar3-3-result.png)

### [3.4. Реализация программы, шифрующей строку, задаваемую пользователем, с помощью алгоритма шифрования ROT13.](https://repl.it/@Rakleed/programming-indepworkinvar3-4)
```python
"""
    Автор: Моисеенко Павел, группа № 1, подгруппа № 2.

    Задание: реализовать программу шифрующую строку, задаваемую
    пользователем, с помощью алгоритма шифрования ROT13.

"""


def rot13(letter):
    if ord("a") + 13 > ord(letter) >= ord("a"):
        return chr(ord(letter) + 13)
    elif ord("z") >= ord(letter) >= ord("a") + 13:
        return chr(ord(letter) - 13)
    else:
        return letter


def main():
    text_to_encrypt = input("Введите текст, который нужно зашифровать: ")
    cipher_text = "".join(list(map(rot13, text_to_encrypt)))
    print("Результат шифрования:", cipher_text)


main()
```
![Result of indepworkinvar3-4](https://github.com/python-basic/sem3-t3-Rakleed/blob/master/src/programming-indepworkinvar3-4-result.png)

# Вариативная самостоятельная работа № 3
### [3.1. ]()
```python

```
![Result of indepworkvar3-1]()

### [3.2. ]()

```python

```
![Result of indepworkvar3-2]()
