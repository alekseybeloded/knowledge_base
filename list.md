# List

## Methods

* ### append(x)

Добавляет элемент x в конец списка.  
Пример:

```python
my_list = [1, 2, 3]  
my_list.append(4)  
print(my_list)  # [1, 2, 3, 4]  
```

* ### extend(iterable)

Расширяет список, добавляя в конец все элементы из указанного iterable.  
Пример:

```python
my_list = [1, 2, 3]  
my_list.extend([4, 5, 6])  
print(my_list)  # [1, 2, 3, 4, 5, 6]
```

* ### insert(i, x)

Вставляет элемент x на позицию i.  
Пример:

```python
my_list = [1, 2, 3]
my_list.insert(1, 10)
print(my_list)  # [1, 10, 2, 3]
```

* ### remove(x)

Удаляет первый элемент в списке, значение которого равно x. Если такого элемента нет, возникает ошибка ValueError.  
Пример:

```python
my_list = [1, 2, 3, 2]
my_list.remove(2)
print(my_list)  # [1, 3, 2]
```

* ### pop([i])

Удаляет и возвращает элемент с позиции i. Если индекс не указан, удаляет и возвращает последний элемент.  
Пример:  

```python
my_list = [1, 2, 3]
last_element = my_list.pop()
print(last_element)  # 3
print(my_list)  # [1, 2]

second_element = my_list.pop(1)
print(second_element)  # 2
print(my_list)  # [1]
```

* ### clear()

Удаляет все элементы из списка.  
Пример:  

```python
my_list = [1, 2, 3]
my_list.clear()
print(my_list)  # []
```

* ### index(x[, start[, end]])

Возвращает индекс первого элемента в списке, значение которого равно x. Можно указать начало и конец поиска. Если элемент не найден, возникает ошибка ValueError.  
Пример:  

```python
my_list = [1, 2, 3, 2]
index_of_2 = my_list.index(2)
print(index_of_2)  # 1

index_of_2_after_2 = my_list.index(2, 2)
print(index_of_2_after_2)  # 3
```

* ### count(x)

Возвращает количество элементов в списке, значение которых равно x, если элемент отсутствует в списке, то возвращается 0.  
Пример:  

```python
my_list = [1, 2, 2, 3, 2]
count_of_2 = my_list.count(2)
print(count_of_2)  # 3
```

* ### sort(key=None, reverse=False)

Сортирует элементы списка на месте (в исходном списке). Можно указать функцию key для сортировки и параметр reverse, чтобы сортировать в обратном порядке.  
Пример:  

```python
my_list = [3, 1, 2]
my_list.sort()
print(my_list)  # [1, 2, 3]

my_list.sort(reverse=True)
print(my_list)  # [3, 2, 1]

my_list = ["apple", "banana", "cherry"]
my_list.sort(key=len)
print(my_list)  # ['apple', 'cherry', 'banana']
```

* ### reverse()

Переворачивает порядок элементов в списке на месте.  
Пример:  

```python
my_list = [1, 2, 3]
my_list.reverse()
print(my_list)  # [3, 2, 1]
```

* ### copy()

Возвращает поверхностную копию списка.  
Пример:  

```python
my_list = [1, 2, 3]
new_list = my_list.copy()
print(new_list)  # [1, 2, 3]
print(new_list is my_list)  # False
```

* ### list(s)

Преобразует s (итерируемый объект) в список.  
Пример:  

```python
my_list = list("hello")
print(my_list)  # ['h', 'e', 'l', 'l', 'o']

my_list = list(range(5))
print(my_list)  # [0, 1, 2, 3, 4]
```

## Deep copy

Глубокая копия списка создается, когда нужно копировать не только сам список, но и все вложенные объекты внутри него. Это важно, если список содержит другие списки, словари или другие изменяемые объекты. В отличие от поверхностной копии, где копируются только ссылки на вложенные объекты, глубокая копия создает новые экземпляры этих вложенных объектов.  

```python
import copy

# Оригинальный список с вложенным списком
original_list = [1, 2, [3, 4]]

# Поверхностная копия
shallow_copy = original_list.copy()

# Глубокая копия
deep_copy = copy.deepcopy(original_list)

# Изменение вложенного списка в оригинале
original_list[2][0] = 99

# Результат
print("Original List:", original_list)        # [1, 2, [99, 4]]
print("Shallow Copy:", shallow_copy)          # [1, 2, [99, 4]]
print("Deep Copy:", deep_copy)                # [1, 2, [3, 4]]
```
