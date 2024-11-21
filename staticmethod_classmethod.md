# @staticmethod, @classmethod

## @staticmethod

**@staticmethod** — это метод, который:

* не связан ни с классом, ни с его экземпляром
* работает как обычная функция, но логически относится к классу
* не может обращаться к данным класса или объекта (нет cls и self)

```python
class MathUtils:
    @staticmethod
    def add(a, b):
        return a + b

# Вызов через класс
print(MathUtils.add(2, 3))  # 5

# Вызов через экземпляр (тоже работает, но это просто функция)
math_utils = MathUtils()
print(math_utils.add(2, 3))  # 5
```

В методе add нет доступа ни к классу MathUtils, ни к его экземпляру. Он просто берёт числа и складывает их.

### Когда использовать @staticmethod?

* Когда метод логически относится к классу, но не использует данные класса или объекта

## @classmethod

**@classmethod** — это метод, который:

* связан с классом, а не с объектом
* принимает первым аргументом сам класс (cls), а не экземпляр (self)
* может работать с атрибутами класса

```python
class Cat:
    species = "Mammal"  # Атрибут класса

    @classmethod
    def get_species(cls):
        return cls.species

# Вызов через класс
print(Cat.get_species())  # Mammal

# Вызов через экземпляр
kitty = Cat()
print(kitty.get_species())  # Mammal
```

Метод get_species работает с атрибутом species, который принадлежит классу, а не объекту.

### Когда использовать @classmethod?

* Когда метод должен работать с данными класса (например, с атрибутами класса)
* Для создания альтернативных конструкторов — методов, которые создают объекты нестандартным способом

### Пример с альтернативным конструктором

Допустим, нам нужно создать объект из строки:

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    @classmethod
    def from_string(cls, data):
        name, age = data.split(",")
        return cls(name, int(age))

# Создание обычным способом
p1 = Person("Alice", 30)

# Создание через строку
p2 = Person.from_string("Bob,25")

print(p2.name, p2.age)  # Bob 25
```

Метод from_string — это альтернативный способ создать объект, используя данные в виде строки.

## Сравнение @staticmethod и @classmethod

```python
class MyClass:
    class_variable = "I am a class variable"

    @staticmethod
    def static_method():
        print("I do not know about the class or object.")

    @classmethod
    def class_method(cls):
        print(f"I know about the class. Class variable is: {cls.class_variable}")

# Вызов
MyClass.static_method()       # I do not know about the class or object.
MyClass.class_method()        # I know about the class. Class variable is: I am a class variable
```

* static_method ничего не знает ни о классе, ни о переменных класса
* class_method работает с атрибутом класса class_variable

## Итог

**@staticmethod:**

* Обычная функция, помещённая в класс для удобства.
* Не зависит от класса или объекта.

**@classmethod:**

* Работает с классом, имеет доступ к его данным (например, атрибутам класса).
* Удобен для создания объектов альтернативными способами.
