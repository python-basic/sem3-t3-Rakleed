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

### [3.2. ](https://repl.it/@Rakleed/programming-indepworkinvar3-2)
```python

```
![Result of indepworkinvar3-2](https://github.com/python-basic/sem3-t3-Rakleed/blob/master/src/programming-indepworkinvar3-2-result.png)

### [3.3. ]()
```python

```
![Result of indepworkinvar3-3](https://github.com/python-basic/sem3-t3-Rakleed/blob/master/src/programming-indepworkinvar3-3-result.png)

### [3.4. Реализация программы, шифрующей строку, задаваемую пользователем, с помощью алгоритма шифрования ROT13.]()
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
