# day9 - 파이썬 기초2

## 제어문

**for문(조건에 따른 순회)**

```
>>> champion_list = ['lux', 'ahri' , 'ezreal','zed']
>>> for champion in champion_list:
...     print(champion)
... 
lux
ahri
ezreal
zed
```

**여러 시퀀스 동시순회(zip)**

```
>>> fruits = ['apple','banana','melon']
>>> colors=['red','yellow','green','purple']
>>> z1=zip(fruits, colors)
>>> z1
<zip object at 0x10ee46508>
>>> list(z1)
[('apple', 'red'), ('banana', 'yellow'), ('melon', 'green')]

>>> z1=zip(fruits, colors)
>>> dict(z1)
{'apple': 'red', 'banana': 'yellow', 'melon': 'green'}
```
zip은 한번 사용하고 사라진다.

**range(start, stop, step)**

```
>>> for x in range(1,5,2):
...     print(x)
... 
1
3
```

## 컴프리헨션 (Comprehension)

### list 컴프리헨션

```
>>> [item for item in range(1,6)]
[1, 2, 3, 4, 5]
```

### list 컴프리헨션 중첩

```
In [6]: ['{}X{}={}'.format(x,y,x*y if y!=9 else str(x*y)+'\n') for x in range(2,10) for y in range(1,10)
   ...: ]
```

## 함수

### 함수의 정의
반복적인 작업을 하는 코드를 재사용이 가능하게 정의해 놓은 것

### 함수의 모든것
ex

```
  1 def make_gugu(num):
  2     a=[(num, y, num*y) for y in range(1,10)]
  3     return a
  4 
  5 def print_gugu(print_type, gugu_list):
  6     def print_gugu_simple():
  7         for item in gugu_list:
  8             print(item)
  9             
 10     def print_gugu_normal():
 11         for item in gugu_list:
 12             for x,y,z in gugu_list:
 13                 print('{} X {} = {}'.format(x,y,z))
 14                 
 15     if print_type == 'simple':
 16         print_gugu_list()
 17     elif print_type == 'normal':
 18         print_gugu_normal()
 19         
 20 def gugu(range_, print_type, make_gugu_function, print_gugu_function):
 21     for num in range_:
 22         print('{val:*>10s}'.format(val='' +str(num) + '단'))
 23 
 24         cur_gugu_list = make_gugu_function(num)
 25 
 26         print_gugu_function(print_type, cur_gugu_list)
 27 
 28         print(' ')
 29 
 30 gugu(range(2,4), 'normal', make_gugu, print_gugu)
 ```

