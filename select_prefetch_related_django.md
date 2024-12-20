# select_related и prefetch_related

В Django — это два метода, которые оптимизируют выполнение запросов к базе данных при работе с связанными объектами. Они помогают избегать "проблемы N+1" (множество лишних запросов к БД при работе с реляционными данными) за счет объединения и предзагрузки данных в одном или нескольких запросах.

## select_related

* **select_related** используется для выполнения JOIN-запросов и загрузки связанных объектов одним SQL-запросом.
* Работает со связями "один к одному" и "многие к одному" (например, ForeignKey, OneToOneField).
* В результате select_related загружает сразу все данные, что позволяет избежать дополнительных запросов при обращении к атрибутам связанных моделей.

### Когда использовать

* если нужно обращаться к атрибутам другой модели, связанной отношением "один к одному" или "многие к одному".

Пример: если у вас есть модель Book, которая ссылается на модель Author, и вам нужно отобразить автора каждой книги, то select_related будет идеальным выбором.

```python
books = Book.objects.select_related('author').all()
```

Здесь будет выполнен один JOIN-запрос для загрузки всех книг вместе с их авторами.

### Особенности

* **select_related** подходит только для ForeignKey и OneToOneField, не работает с отношениями "многие ко многим" (ManyToManyField).
* Поскольку данные подгружаются в один запрос, select_related может увеличить объем данных и время выполнения запроса, если связано большое количество объектов или таблица слишком большая.
* Можно использовать select_related с вложенными связями, передав путь через двойное подчеркивание: .select_related('author__publisher').

## prefetch_related

* **prefetch_related** выполняет отдельные запросы к базе данных для каждой указанной связанной модели, а затем кэширует и связывает данные на уровне Python.
* Работает с связями "многие к одному", "один к одному", "многие ко многим".
* Позволяет получить связанные объекты за несколько запросов, но без выполнения JOIN-запроса.

### Когда использовать

* если нужно загрузить связанные объекты для отношений "многие ко многим" или "один ко многим", либо когда объем данных слишком велик для JOIN-запроса.

* Например, если вам нужно загрузить книги и все жанры для каждой книги (где жанры связаны ManyToMany).

```python
books = Book.objects.prefetch_related('genres').all()
```

Здесь будет выполнено два запроса: один для загрузки книг и один для загрузки жанров, связанных с этими книгами, а затем Django автоматически распределит жанры по соответствующим книгам.

### Особенности

* **prefetch_related** можно использовать с любой связью, включая ManyToMany и GenericForeignKey.
* Может потребовать больше оперативной памяти, так как данные кешируются на уровне Python, а не на уровне SQL.
* **prefetch_related** также поддерживает вложенные связи через двойное подчеркивание, например, .prefetch_related('genres__subgenres').
* Поддерживает передачу кастомных QuerySet, что позволяет фильтровать или сортировать связанные данные.

## Когда выбрать

* Используйте select_related, когда у вас один к одному или многие к одному и не требуется большая вложенность данных.
* Используйте prefetch_related, если у вас многие ко многим, один ко многим, либо если данные очень большие и JOIN-запрос может оказаться менее эффективным.
