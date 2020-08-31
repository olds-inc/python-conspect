# Генераторы списков

Данный механизм позволяет упростить код создания или мапинга списков или других перечисляемых объектов

Общая структура:

1. Выражение результат которого будет класть в список
2. Цикл (или несколько циклов)
3. Условный оператор, определяющий попадет элемент в список или нет

```python
(values) = [ (expression) for (value) in (collection) ]
```

Примеры

```python
# list of even numbers from [0 to 10)
even_numbers = [i for i in range(10) if i % 2 == 0]
print(even_numbers)  # [0, 2, 4, 6, 8]

# list of square numbers from [0 to 10)
square_numbers = [i ** 2 for i in range(10)]
print(square_numbers)  # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

# list of pairs where y == x
tuples_list = [(x, y) for x in range(3) for y in range(3) if y == x]
print(tuples_list)  # <class 'generator'>
```