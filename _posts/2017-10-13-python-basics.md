---
title: python 基礎
tags: [python]
---

# 基本的資料型別

### int
```python
>>> 100
```

### float
```python
>>> 0.5
```

### bool
```python
>>> True
```

### string
```python
>>> 'apple'
```

### list
```python
# list 的元素不需要具備相同的型別
>>> sample_list = [3, True, "102", 1]

# Adding Items to a List
>>> sample_list.append('murloc')
>>> print(sample_list)
[3, True, '102', 1, 'murloc']

# Removing Items from a List
>>> del sample_list[1]
>>> print(sample_list)
[3, '102', 1, 'murloc']

# append a list to a list
>>> print([1, 3] + ['I', 'over', 'hit'])
[1, 3, 'I', 'over', 'hit']
```

### tuple 
```python
>>> meaningless_words = (1, "hello", False)
>>> print(meaningless_words[1])
"hello"

# tuple is immutable
>>> meaningless_words[1] = "hi"
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

### map
```python
>>> favorite_sports = {'Ralph Williams' : 'Football', 'Michael Tippett' : 'Basketball', 'Edward Elgar' : 'Baseball', 'Frank Bridge' : 'Rugby'}
``` 
