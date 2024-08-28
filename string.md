# String

## Methods

* ### str.lower()

Преобразует строку в нижний регистр.  
Пример:

```python
s = "Hello World"
print(s.lower())  # "hello world"
```

* ### str.upper()

Преобразует строку в верхний регистр.  
Пример:

```python
s = "Hello World"
print(s.upper())  # "HELLO WORLD"
```

* ### str.capitalize()

Преобразует первую букву строки в верхний регистр, остальные в нижний.  
Пример:

```python
s = "hello world"
print(s.capitalize())  # "Hello world"
```

* ### str.title()

Преобразует первую букву каждого слова в верхний регистр.  
Пример:

```python
s = "hello world"
print(s.title())  # "Hello World"
```

* ### str.strip()

Удаляет пробелы (или другие символы) в начале и в конце строки.  
Пример:  

```python
s = "  hello world  "
print(s.strip())  # "hello world"
```

* ### str.lstrip()

Удаляет пробелы (или другие символы) в начале строки.  
Пример:  

```python
s = "  hello world  "
print(s.lstrip())  # "hello world  "
```

* ### str.rstrip()

Удаляет пробелы (или другие символы) в конце строки.  
Пример:  

```python
s = "  hello world  "
print(s.rstrip())  # "  hello world"
```

* ### str.replace(old, new)

Заменяет все вхождения подстроки old на new.  
Пример:  

```python
s = "Hello World"
print(s.replace("World", "Python"))  # "Hello Python"
```

* ### str.find(sub)

Возвращает индекс первого вхождения подстроки sub. Возвращает -1, если подстрока не найдена.  
Пример:  

```python
s = "Hello World"
print(s.find("World"))  # 6
```

* ### str.count(sub)

Возвращает количество вхождений подстроки sub.  
Пример:  

```python
s = "banana"
print(s.count("a"))  # 3
```

* ### str.startswith(prefix)

Проверяет, начинается ли строка с подстроки prefix.  
Пример:  

```python
s = "Hello World"
print(s.startswith("Hello"))  # True
```

* ### str.endswith(suffix)

Проверяет, заканчивается ли строка подстрокой suffix.  
Пример:  

```python
s = "Hello World"
print(s.endswith("World"))  # True
```

* ### str.isdigit()

Проверяет, состоит ли строка только из цифр.  
Пример:  

```python
s = "12345"
print(s.isdigit())  # True
```

* ### str.isalpha()

Проверяет, состоит ли строка только из букв.  
Пример:  

```python
s = "Hello"
print(s.isalpha())  # True
```

* ### str.isalnum()

Проверяет, состоит ли строка только из букв и цифр.  
Пример:  

```python
s = "Hello123"
print(s.isalnum())  # True
```

* ### str.split(delimiter)

Разбивает строку на список подстрок по разделителю delimiter.  
Пример:  

```python
s = "Hello,World,Python"
print(s.split(","))  # ["Hello", "World", "Python"]
```

* ### str.join(iterable)

Соединяет элементы iterable (список, кортеж и т.д.) в строку, используя строку str как разделитель.  
Пример:  

```python
s = "-"
words = ["Hello", "World", "Python"]
print(s.join(words))  # "Hello-World-Python"
```

* ### str.zfill(width)

Заполняет строку нулями слева до длины width.  
Пример:  

```python
s = "42"
print(s.zfill(5))  # "00042"
```

* ### str.center(width)

Выравнивает строку по центру, добавляя пробелы до длины width.  
Пример:  

```python
s = "Hello"
print(s.center(10))  # "  Hello   "
```

* ### str.ljust(width)

Выравнивает строку по левому краю, добавляя пробелы до длины width.  
Пример:  

```python
s = "Hello"
print(s.ljust(10))  # "Hello     "
```

* ### str.rjust(width)

Выравнивает строку по правому краю, добавляя пробелы до длины width.  
Пример:  

```python
s = "Hello"
print(s.rjust(10))  # "     Hello"
```
