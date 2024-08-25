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
