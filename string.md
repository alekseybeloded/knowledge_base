# String

## Methods

* ### .capitalize()

Преобразует первый символ строки в верхний регистр, остальные символы — в нижний.

```python
text = "hello world"
print(text.capitalize())  # "Hello world"
```

* ### .casefold()

Приводит строку к нижнему регистру, оптимизированному для сравнения, нечувствительного к регистру.

```python
text = "Straße"
print(text.casefold())  # "strasse"
```

* ### .center(width, fillchar=' ')

Выравнивает строку по центру, добавляя символы fillchar с обеих сторон.

```python
text = "hello"
print(text.center(10, '-'))  # "--hello---"
```

* ### .count(sub, start=0, end=len(string))

Считает количество вхождений подстроки sub в строке.

```python
text = "banana"
print(text.count("a"))  # 3
```

* ### .encode(encoding='utf-8', errors='strict')

Кодирует строку в указанный формат (по умолчанию UTF-8).  

```python
text = "hello"
print(text.encode())  # b'hello'
```

* ### .endswith(suffix, start=0, end=len(string))

Проверяет, заканчивается ли строка указанным suffix.  

```python
text = "example.txt"
print(text.endswith(".txt"))  # True
```

* ### .expandtabs(tabsize=8)

Заменяет символы табуляции (\t) пробелами, используя указанный размер табуляции.  

```python
text = "1\t2\t3"
print(text.expandtabs(4))  # "1   2   3"
```

* ### .find(sub, start=0, end=len(string))

Возвращает индекс первого вхождения подстроки sub. Если подстрока не найдена, возвращает -1.  

```python
text = "hello world"
print(text.find("world"))  # 6
```

* ### .format(*args, **kwargs)

Используется для форматирования строки.  

```python
template = "Hello, {}!"
print(template.format("Alice"))  # "Hello, Alice!"
```

* ### .format_map(mapping)

Форматирует строку, используя словарь для подстановки значений.  

```python
data = {"name": "Alice", "age": 25}
template = "Name: {name}, Age: {age}"
print(template.format_map(data))  # "Name: Alice, Age: 25"
```

* ### .index(sub, start=0, end=len(string))

Возвращает индекс первого вхождения подстроки sub. Если подстрока не найдена, вызывает исключение ValueError.  

```python
text = "hello world"
print(text.index("world"))  # 6
```

* ### .isalnum()

Возвращает True, если строка состоит только из буквенно-цифровых символов и не пуста.  

```python
text = "Hello123"
print(text.isalnum())  # True
```

* ### .isalpha()

Возвращает True, если строка состоит только из буквенных символов.  

```python
text = "Hello"
print(text.isalpha())  # True
```

* ### .isascii()

Возвращает True, если строка содержит только ASCII-символы.  

```python
text = "Hello!"
print(text.isascii())  # True
```

* ### .isdigit()

Возвращает True, если строка состоит только из цифр.  

```python
text = "123"
print(text.isdigit())  # True
```

* ### .islower()

Возвращает True, если все символы строки в нижнем регистре.  

```python
text = "hello"
print(text.islower())  # True
```

* ### .isupper()

Возвращает True, если все символы строки в верхнем регистре.  

```python
text = "HELLO"
print(text.isupper())  # True
```

* ### .isspace()

Возвращает True, если строка состоит только из пробельных символов.  

```python
text = "   "
print(text.isspace())  # True
```

* ### .istitle()

Возвращает True, если строка оформлена как заголовок (каждое слово начинается с заглавной буквы).  

```python
text = "Hello World"
print(text.istitle())  # True
```

* ### .join(iterable)

Объединяет элементы последовательности iterable, вставляя между ними строку.  

```python
separator = ", "
items = ["apple", "banana", "cherry"]
print(separator.join(items))  # "apple, banana, cherry"
```

* ### .ljust(width, fillchar=' ')

Выравнивает строку влево, добавляя символы fillchar справа.  

```python
text = "hello"
print(text.ljust(10, '-'))  # "hello-----"
```

### .lower()

Приводит строку к нижнему регистру.

```python
text = "HELLO"
print(text.lower())  # "hello"
```

### .lstrip(chars=None)

Удаляет указанные символы chars с начала строки.

```python
text = "   hello"
print(text.lstrip())  # "hello"
```

### .partition(separator)

Разделяет строку на три части: до разделителя, сам разделитель и после него.

```python
text = "key=value"
print(text.partition("="))  # ('key', '=', 'value')
```

### .replace(old, new, count=-1)

Заменяет вхождения old на new. Если указан count, заменяет только указанное количество вхождений.

```python
text = "banana"
print(text.replace("a", "o", 2))  # "bonona"
```

### .rfind(sub, start=0, end=len(string))

Возвращает индекс последнего вхождения sub. Если не найдено, возвращает -1.

```python
text = "hello world"
print(text.rfind("o"))  # 7
```

### .rindex(sub, start=0, end=len(string))

Как .rfind(), но вызывает исключение, если подстрока не найдена.

```python
text = "hello world"
print(text.rindex("o"))  # 7
```

### .rjust(width, fillchar=' ')

Выравнивает строку вправо, добавляя символы fillchar слева.

```python
text = "hello"
print(text.rjust(10, '-'))  # "-----hello"
```

### .rstrip(chars=None)

Удаляет указанные символы chars с конца строки.

```python
text = "hello   "
print(text.rstrip())  # "hello"
```

### .split(separator=None, maxsplit=-1)

Разделяет строку на список подстрок, используя указанный разделитель.

```python
text = "apple,banana,cherry"
print(text.split(","))  # ['apple', 'banana', 'cherry']
```

### .splitlines(keepends=False)

Разделяет строку по строкам, сохраняя (True) или удаляя (False) символы переноса строк.

```python
text = "Line1\nLine2\nLine3"
print(text.splitlines())  # ['Line1', 'Line2', 'Line3']
```

### .startswith(prefix, start=0, end=len(string))

Проверяет, начинается ли строка с указанного префикса.

```python
text = "hello world"
print(text.startswith("hello"))  # True
```

### .strip(chars=None)

Удаляет указанные символы chars с начала и конца строки.

```python
text = "   hello   "
print(text.strip())  # "hello"
```

### .swapcase()

Меняет регистр всех символов в строке на противоположный.

```python
text = "Hello World"
print(text.swapcase())  # "hELLO wORLD"
```

### .title()

Преобразует строку в формат заголовка (первая буква каждого слова — заглавная).

```python
text = "hello world"
result = text.title()
print(result)  # Вывод: "Hello World"
```

### .upper()

Преобразует все символы строки в верхний регистр.

```python
text = "hello"
print(text.upper())  # "HELLO"
```

### .zfill(width)

Дополняет строку нулями слева, чтобы её длина стала равной width.

```python
text = "42"
print(text.zfill(5))  # "00042"
```
