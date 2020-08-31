# Ошибки и исключения

В python существуект 2 типа ошибок:

1. Syntax error - ошибки возникающие внутри интерпретатора в момент компиляции в случае если мы допустили ошибку в синтаксисе программы
2. Exceptions - исключения возникающие в ходе выполнения программы

## Обработка исключения _try-except-else-finally_

Для обработки исключение существуют следующие виды конструкций:

```python
try:
    print()
except TypeError:
    print()
```

```python
try:
    print()
except (TypeError, ZeroDivisionError):
    print()
```

```python
try:
    print()
except TypeError as e:
    print(e)
```

```python
def divide(x, y):
    try:
        result = x / y
    except ZeroDivisionError:
        print('devision by zero')
    else:
        print('result is', result)
    finally:
        print('finally will be run even if we have uncaught exception')
```

Блок _else_ сработает в том случае, если мы не поймали исключение

Важно помнить что блок _finally_ отрабатывает всегда, даже если в коде возникла ошибка которую мы не обработали или ошибки не возникло вовсе

Каждый оператор _except_ сравнивает пойманное исключение с помощью `isinstance(e, Exception)`, если результат вызова `isinstance(e, Exception) == True` - заходим в блок данного обработчика, иначе проверяем следующие операторы _except_ по цепочке

Учитывая вышеупомянутое свойство оператора _except_ и иерархию наследования классов исключений в python, для того чтобы корректно обработать исключение, следует сначала указывать наиболее специфичные исключения (которые ниже в иерархии наследования) а потом наименее специфичные (которые выше в иерархии наследования), например сначала нужно обрабатывать __ZeroDivisionError__ а потом __ArithmeticError__  иначе __ArithmeticError__ проглотит  __ZeroDivisionError__

## Оператор __raise__

Для того чтобы сгенерировать иключение применяется оператор _raise_, который бросает экземпляр созданного нами исключения

Чтобы мы могли бросить свое исключение, его класс должен быть предком __BaseException__

```python
if number < 1:
    raise ValueError('number lesst than 1'_)
```