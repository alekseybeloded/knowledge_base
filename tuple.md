# Tuple

## Methods

* ### count()

Возвращает количество вхождений заданного элемента в кортеже, если элемент отсутствует, возвращается 0.  
  
Пример:

```python
t = (1, 2, 3, 2, 2, 4)
print(t.count(2))  # Вывод: 3
```

* ### index()

Возвращает индекс первого вхождения заданного элемента в кортеже. Если элемент не найден, возникает ошибка ValueError.  
Пример:

```python
t = (1, 2, 3, 4)
print(t.index(3))  # Вывод: 2

# Если элемент не найден
# t.index(5)  # Возникнет ValueError
```

## Операции с кортежами

* ### Конкатенация

Можно объединять два кортежа с помощью оператора +  
Пример:

```python
t1 = (1, 2, 3)
t2 = (4, 5, 6)
t3 = t1 + t2
print(t3)  # Вывод: (1, 2, 3, 4, 5, 6)
```

* ### Повторение

Можно повторять кортеж несколько раз с помощью оператора *  
Пример:

```python
t = (1, 2, 3)
t2 = t * 3
print(t2)  # Вывод: (1, 2, 3, 1, 2, 3, 1, 2, 3)
```

* ### Доступ по индексу

Можно получить элемент по его индексу с помощью квадратных скобок.  
Пример:

```python
t = (1, 2, 3)
print(t[0])  # Вывод: 1
print(t[-1])  # Вывод: 3
```

* ### Срезы

Можно получить часть кортежа с помощью срезов.  
Пример:

```python
t = (1, 2, 3, 4, 5)
print(t[1:3])  # Вывод: (2, 3)
```

* ### Проверка на вхождение

Можно проверить, содержится ли элемент в кортеже, используя оператор in  
Пример:

```python
t = (1, 2, 3)
print(2 in t)  # Вывод: True
print(4 in t)  # Вывод: False
```