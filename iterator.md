# Iterator

Итераторы — это объекты, которые позволяют перебирать элементы коллекций, например списков, кортежей или других последовательностей, по одному элементу за раз. В Python итераторы реализуют итерационный протокол, который состоит из двух методов:

1. * __iter__(): возвращает сам итератор.
2. * __next__(): возвращает следующий элемент последовательности, а при завершении последовательности выбрасывает исключение StopIteration.

## Как работают итераторы?

Итератор позволяет циклически перебирать элементы последовательности с помощью цикла for или вручную с использованием функции next().  

```python
# Пример использования итератора для списка
my_list = [1, 2, 3]
my_iter = iter(my_list)  # Преобразуем список в итератор

# Получаем элементы вручную с помощью next()
print(next(my_iter))  # 1
print(next(my_iter))  # 2
print(next(my_iter))  # 3
# Если попробовать вызвать next() ещё раз, произойдет StopIteration
# print(next(my_iter))  # StopIteration
```

В Python такие структуры данных, как списки, кортежи, множества и строки, уже являются итерируемыми объектами, т.е. вы можете получить их итератор с помощью функции iter(). При итерации с помощью for, Python неявно использует итератор.  

Пример с циклом for:  

```python
my_list = [1, 2, 3]

for item in my_list:
    print(item)
```

Этот код делает то же самое, что и:  

```python
my_list = [1, 2, 3]
my_iter = iter(my_list)

while True:
    try:
        item = next(my_iter)
        print(item)
    except StopIteration:
        break
```

## Реализация протокола итератора

Вы можете создать свой собственный итератор, реализовав протокол итератора, т.е. методы __iter__() и __next__().  

Пример пользовательского итератора:

```python
class MyIterator:
    def __init__(self, data):
        self.data = data
        self.index = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self.index < len(self.data):
            result = self.data[self.index]
            self.index += 1
            return result
        else:
            raise StopIteration

# Использование пользовательского итератора
my_iter = MyIterator([1, 2, 3])

for item in my_iter:
    print(item)
```

## Как работает пользовательский итератор

1. * Метод __iter__() просто возвращает сам объект, чтобы его можно было использовать в циклах for или других местах, где требуется итерация.  
2. * Метод __next__() возвращает следующий элемент, пока элементы не закончатся. Если элементы закончились, вызывается исключение StopIteration.  

Пример ручного вызова:

```python
my_iter = MyIterator([1, 2, 3])
print(next(my_iter))  # 1
print(next(my_iter))  # 2
print(next(my_iter))  # 3
# Следующий вызов next() приведет к StopIteration
# print(next(my_iter))  # StopIteration
```

## Генераторы и итераторы

В Python генераторы являются упрощённым способом создания итераторов. Они используют ключевое слово yield вместо return, что позволяет сохранять текущее состояние функции и продолжать выполнение с этого места при следующем вызове. Каждый раз, когда функция-генератор вызывает yield, она приостанавливает свою работу и возвращает значение, а затем при следующем вызове продолжает с того места, где остановилась.  

Пример генератора:

```python
def my_generator():
    yield 1
    yield 2
    yield 3

gen = my_generator()

print(next(gen))  # 1
print(next(gen))  # 2
print(next(gen))  # 3
# Следующий вызов next() приведет к StopIteration
# print(next(gen))  # StopIteration
```

## Итог

* Итерируемые объекты реализуют метод __iter__(), который возвращает итератор.
* Итераторы реализуют метод __next__() для получения следующего элемента и вызывают StopIteration, когда элементы заканчиваются.
* Генераторы — это способ создания итераторов с использованием функции yield.  

## Важные моменты

* Итерируемые объекты можно использовать в цикле for.
* Итераторы позволяют перебирать элементы с помощью функции next().
* Реализуя итерационный протокол, можно создавать собственные итераторы, управляя процессом итерации вручную.
