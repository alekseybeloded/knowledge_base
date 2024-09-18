# Algorithms

## Selection sort

```python
def find_smallest_index(array):
    smallest_index = 0
    smallest_number = array[smallest_index]
    for i in range(1, len(array)):
        if array[i] < smallest_number:
            smallest_index = i
            smallest_number = array[i]
    return smallest_index


def selection_sort(array):
    new_arr = []
    while array:
        new_arr.append(array.pop(find_smallest_index(array)))
    return new_arr
```

## Recursion

Пример 1:

```python
def factorial_recursion(number):
    if number > 1: # если условие ложно, выполняется базовый случай
        number = number * factorial_recursion(number - 1) # рекурсивный случай
    return number
```

Пример 2:

```python
def sum_recursion(list):
    if list == []: # базовый случай
        return 0 
    return list[0] + sum_recursion(list[1:]) # рекурсивный случай
```

## Quick sort

```python
def quick_sort(array):
    if len(array) < 2:
        return array
    pivot = array[0]
    less = [i for i in array[1:] if i < pivot]
    greater = [i for i in array[1:] if i > pivot]
    return quick_sort(less) + [pivot] + quick_sort(greater)
```

## Breadth-First Search

```python
from collections import deque

# Граф в виде словаря (модель связей между людьми)
graph = {
    "you": ["alice", "bob", "claire"],
    "bob": ["anuj", "peggy"],
    "alice": ["peggy"],
    "claire": ["thom", "jonny"],
    "anuj": [],
    "peggy": [],
    "thom": [],
    "jonny": []
}

def person_is_seller(person):
    # Логика проверки, является ли человек продавцом манго (например, если имя заканчивается на 'm')
    return person[-1] == 'm'

def search(name):
    # Очередь для проверки (используем очередь для реализации BFS)
    search_queue = deque()
    search_queue += graph[name]  # Добавляем всех соседей начального узла в очередь
    
    # Массив для отслеживания уже проверенных людей
    searched = []

    # Пока в очереди есть люди для проверки
    while search_queue:
        # Извлекаем первого человека из очереди
        person = search_queue.popleft()
        
        # Проверяем этого человека только в том случае, если его еще не проверяли
        if person not in searched:
            # Если этот человек — продавец манго, выводим результат и возвращаем True
            if person_is_seller(person):
                print(person + " is a mango seller!")
                return True
            else:
                # Если это не продавец, добавляем его соседей в очередь
                search_queue += graph[person]
                # Помечаем этого человека как проверенного
                searched.append(person)
    
    # Если не нашли продавца манго, возвращаем False
    return False

# Запуск поиска с начальной вершины "you"
search("you")
```
