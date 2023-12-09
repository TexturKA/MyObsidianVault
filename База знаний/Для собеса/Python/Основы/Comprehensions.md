### Что такое списковое включение и генераторные выражения?

**Генераторное выражение** или **абстракция** - это конструкторы, позволяющие создавать последовательности из других последовательностей.

**Списковое включение** - разновидность генераторного выражения, где конечная последовательность – список.

Пример использования генераторных выражений: 
```python
data = (  
    ("key1", "value1"),  
    ("key2", "value2"),  
    ("key3", "value2"),  
)  
listcomp = [value for key, value in data if key != "key1"]  # Списковое включение
setcomp = {value for key, value in data if key != "key1"}  # Абстракция множества
dictcomp = {key: value for key, value in data if key != "key1"}  # Абстракция словаря
genexp = (value for key, value in data if key != "key1")  # Генераторное выражение
print(listcomp, setcomp, dictcomp, genexp, sep="\n")  
# ['value2', 'value2']  
# {'value2'}  
# {'key2': 'value2', 'key3': 'value2'}  
# <generator object <genexpr> at 0x000001BA616BF6B0>  
for item in genexp:  
    print(item, end=" ")  
# value2 value2
```