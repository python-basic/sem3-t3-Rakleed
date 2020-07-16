# Содержание
- [ЛР № 10]()
- [ЛР № 11]()
- [ИСР № 3](#инвариативная-самостоятельная-работа--3)
    - [1 задание](#31-создание-аннотированного-списка-библиотек-для-работы-с-текстом-в-python)
    - [2 задание](#32-разработка-сценария-с-реализацией-операции-поиска-подстроки-в-тексте)
    - [3 задание](#33-создание-скрипта-для-считывания-данных-справочных-логов-из-текстового-файла-и-преобразования-их-в-csv-формат-с-последующей-записью-в-новый-файл)
    - [4 задание](#34-реализация-программы-шифрующей-строку-задаваемую-пользователем-с-помощью-алгоритма-шифрования-rot13)
- [ВСР № 3](#вариативная-самостоятельная-работа--3)
    - [1 задание](#31-реализация-программы-игры-угадай-число-в-которой-для-вывода-на-экран-информации-используется-метод-format)
    - [2 задание](#32-реализация-программы-с-шифрованием-текста-с-помощью-шифра-цезаря-и-возможностью-задания-сдвига)

# [Лабораторная работа № 10](https://repl.it/@Rakleed/programming-lab10)
```python

```
![Result of lab10](https://github.com/python-basic/sem3-t3-Rakleed/blob/master/src/programming-lab10-result.png)

# [Лабораторная работа № 11](https://repl.it/@Rakleed/programming-lab11)
```python

```
![Result of lab11](https://github.com/python-basic/sem3-t3-Rakleed/blob/master/src/programming-lab11-result.png)

# Инвариативная самостоятельная работа № 3
### 3.1. Создание аннотированного списка библиотек для работы с текстом в Python.
[Результат.](https://github.com/python-basic/sem3-t3-Rakleed/blob/master/src/programming-indepworkinvar3-1-result.pdf)

### [3.2. Разработка сценария с реализацией операции поиска подстроки в тексте.](https://repl.it/@Rakleed/programming-indepworkinvar3-2)
```python
"""
    Автор: Моисеенко Павел, группа № 1, подгруппа № 2.

    ИСР 3.2. Задание: разработайте сценарий с реализацией операции поиска подстроки в тексте.

"""


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


def main():
    search_string = input("Введите строку. ")
    what_to_find = input("Что бы вы хотели найти? ")
    all_occurrences(search_string, what_to_find)


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
### [3.1. Реализация программы-игры «Угадай число», в которой для вывода на экран информации используется метод format.](https://repl.it/@Rakleed/programming-indepworkvar3-1)
```python
"""
    Автор: Моисеенко Павел, группа № 1, подгруппа № 2.

    ИСР 3.3. Задание: реализовать программу-игру «Угадай число», в
    которой для вывода на экран информации использовать метод format.

"""


def guess_number(a, b):
    import random
    random_number = random.randint(a, b)
    user_number = -0.5
    while random_number != user_number:
        user_number = int(input('Введите число: '))
        if user_number < random_number:
            print('Вы не угадали, введите число больше.')
        elif user_number > random_number:
            print('Вы не угадали, введите число меньше.')
    print('Вы угадали число {} из диапазона [{}, {}]!'.format(random_number,
                                                             a, b))


def main():
    print('Введите диапазон для игры.')
    a = int(input('Нижний предел: '))
    b = int(input('Верхний предел: '))
    guess_number(a, b)


main()
```
![Result of indepworkvar3-1](https://github.com/python-basic/sem3-t3-Rakleed/blob/master/src/programming-indepworkvar3-1-result.png)

### [3.2. Реализация программы с шифрованием текста с помощью шифра Цезаря и возможностью задания сдвига.](https://repl.it/@Rakleed/programming-indepworkvar3-2)

```python
"""
    Автор: Моисеенко Павел, группа № 1, подгруппа № 2.

    ВСР 3.2. Задание: реализовать программу шифрующую строку, задава-
    емую пользователем, с помощью алгоритма шифрования, использующего
    сдвиг на определенное количество знаков (шифр Цезаря). Сдвиг
    задается пользователем.

"""


def caesar_cipher(shift, text_to_encrypt):
    cipher_text = ''
    for i in text_to_encrypt:
        if 'a' <= i <= 'z':
            algorithm = chr((ord(i) + shift - ord('a')) % 26 + ord('a'))
            cipher_text += algorithm
        elif 'A' <= i <= 'Z':
            algorithm = chr((ord(i) + shift - ord('A')) % 26 + ord('A'))
            cipher_text += algorithm
        elif 'а' <= i <= 'я':
            algorithm = chr((ord(i) + shift - ord('а')) % 30 + ord('а'))
            cipher_text += algorithm
        elif 'А' <= i <= 'Я':
            algorithm = chr((ord(i) + shift - ord('А')) % 30 + ord('А'))
            cipher_text += algorithm
        else:
            cipher_text += i
    return cipher_text


def main():
    text_to_encrypt = input('Введите строку: ')
    shift = int(input('Введите сдвиг: '))
    print('Получившаяся строка:', caesar_cipher(shift, text_to_encrypt))


main()
```
![Result of indepworkvar3-2](https://github.com/python-basic/sem3-t3-Rakleed/blob/master/src/programming-indepworkvar3-2-result.png)
