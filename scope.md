# Область видимости

Область видимости - фрагмент программы в котором локальное пространство имен доступно напрямую

Например все что находится в теле функции фактически является областью видимости этой функции. Или все что находится в пространстве имен main являет собой область видимости пространства имен main

Фактически для каждой функции ее областью видимости является локальное пространство имен генерируемое этой функцией

## 4 категории областей видимости

1. Локальная область видимости (local scope)
2. Закрывающая область видимости (enclosing scope)
3. Глобальная область видимости (global scope)
4. Область видимости builtins (builtins scope)

Для каждой области видимости у нас есть соответствующее ей пространство имен, и мы ищем переменные в этих пространствах имен. Порядок областей видимости: local, non-local, global, builtins.

```
local scope -> non-local scope -> global scope -> builtins scope
```

## Ключево слово global

## Ключево слово nonlocal