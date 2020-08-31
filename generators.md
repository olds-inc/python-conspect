# Генераторы

_Генераторы_ это тоже _итерируемые_ объекты, но прочитать их можно лишь один раз. Это связано с тем, что они не хранят значения в памяти, а генерируют их на лету

С помощью генераторов в языке python реализуется концепция отложенного исполнения, сначала выполняется тело до оператора __yield__ и возвращается генератор, функция на этом месте останавливается и запоминает свое состояние, при следующем вызове функция начнет выполняться с места на котором остановился, пока не дойдет до следующего __yield__, если тело функции выполнится до конца а оператора __yield__ не встретится или встретится оператор __return__, будет выброшено исключение __StopIteration__ т.е. перебираемых значений не останется

__Yield__ это ключевое слово, которое используется примерно как __return__ — отличие в том, что функция вернёт _генератор_

```python
def simple_gen():
    print('checkpoint 1')
    yield 1
    print('checkpoint 2')
    yield 2
    print('checkpoint 3')
    return

gen = simple_gen()

one = next(gen)  # printed checkpoint 1
two = next(gen)  # printed checkpoint 2
# next(gen)  # StopIteration

print(one)  # 1
print(two)  # 2
```

Генератор можно получить с помощью синтаксиса _List Comprehension_

```python
tuples_list = ((x, y) for x in range(3) for y in range(3) if y >= x)
print(type(tuples_list))  # <class 'generator'>
```