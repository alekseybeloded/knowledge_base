# Dict

## Methods

* ### dict.get(key[, default])

Возвращает значение для ключа key, если ключ существует. Если ключа нет, возвращает значение по умолчанию default, если оно указано, или None.  
Пример:  

```python
d = {'a': 1, 'b': 2}
print(d.get('a'))  # 1
print(d.get('c', 0))  # 0  
```

* ### dict.keys()

Возвращает объект представления (view object), содержащий все ключи в словаре.  
Пример:  

```python
d = {'a': 1, 'b': 2}
print(d.keys())  # dict_keys(['a', 'b'])  
```

* ### dict.values()

Возвращает объект представления, содержащий все значения в словаре.  
Пример:  

```python
d = {'a': 1, 'b': 2}
print(d.values())  # dict_values([1, 2])  
```

* ### dict.pop(key[, default])

Удаляет элемент по ключу key и возвращает его значение. Если ключа нет, возвращает default (если указано) или вызывает ошибку KeyError.  
Пример:  

```python
d = {'a': 1, 'b': 2}
print(d.pop('a'))  # 1
print(d)  # {'b': 2}  
```

* ### dict.popitem()

Удаляет и возвращает последнюю добавленную пару ключ-значение в словаре в виде кортежа. Если словарь пуст, вызывает KeyError.  
Пример:  

```python
d = {'a': 1, 'b': 2}
print(d.popitem())  # ('b', 2)
print(d)  # {'a': 1}  
```

* ### dict.update([other])

Обновляет словарь, добавляя пары ключ-значение из другого словаря или итерируемого объекта other.  
Пример:  

```python
d = {'a': 1, 'b': 2}
d.update({'b': 3, 'c': 4})
print(d)  # {'a': 1, 'b': 3, 'c': 4}  
```

* ### dict.clear()

Удаляет все элементы из словаря.  
Пример:  

```python
d = {'a': 1, 'b': 2}
d.clear()
print(d)  # {}
```

* ### dict.copy()

Возвращает поверхностную копию словаря.  
Пример:  

```python
d = {'a': 1, 'b': 2}
d_copy = d.copy()
print(d_copy)  # {'a': 1, 'b': 2}  
```

* ### dict.fromkeys(iterable[, value])

Создает новый словарь с ключами из iterable и значениями, равными value (по умолчанию None).  
Пример:  

```python
keys = ['a', 'b', 'c']
d = dict.fromkeys(keys, 0)
print(d)  # {'a': 0, 'b': 0, 'c': 0}
```

* ### dict.setdefault(key[, default])

Если ключ key существует, возвращает его значение. Если нет, добавляет в словарь ключ key с значением default (по умолчанию None) и возвращает его.  
Пример:  

```python
d = {'a': 1}
print(d.setdefault('a', 0))  # 1
print(d.setdefault('b', 2))  # 2
print(d)  # {'a': 1, 'b': 2}  
```

## Deep copy

Для создания глубокой копии словаря в Python можно использовать модуль copy, который предоставляет функцию deepcopy(). Глубокая копия создаёт новый словарь, в котором копируются не только сами ключи и значения, но и все вложенные структуры данных, такие как списки, словари и т.д.  

Пример:

```python
import copy

# Исходный словарь
original_dict = {
    'a': 1,
    'b': [1, 2, 3],
    'c': {'x': 10, 'y': 20}
}

# Создание глубокой копии
deep_copied_dict = copy.deepcopy(original_dict)

# Изменение глубокой копии
deep_copied_dict['b'].append(4)
deep_copied_dict['c']['z'] = 30

# Исходный словарь остается неизменным
print(original_dict) # {'a': 1, 'b': [1, 2, 3], 'c': {'x': 10, 'y': 20}}
print(deep_copied_dict) # {'a': 1, 'b': [1, 2, 3, 4], 'c': {'x': 10, 'y': 20, 'z': 30}}
```
