# About itertools

```
In [1]: from itertools import *

In [2]: print(*accumulate(range(5)))
0 1 3 6 10

In [3]: # accumulate - накапливание суммы

In [4]: print(*chain(range(5), ['a', 'b']))
0 1 2 3 4 a b

In [5]: # chain - создает цепь с iterable объектов

In [6]: print(*combinations([1,2,3], 2))
(1, 2) (1, 3) (2, 3)

In [7]: # комбинации

In [8]: print(*combinations_with_replacement([1,2,3], 2))
(1, 1) (1, 2) (1, 3) (2, 2) (2, 3) (3, 3)

In [9]: # комбинации с одинаковыми элементами

In [10]: print(*compress([1,2,3], [True, False, True]))
1 3

In [11]: print(*islice(count(), 5))
0 1 2 3 4

In [12]: # count - бесконечная арифметическая прогрессия с первым членом start и
    ...:  шагом step.

In [13]: # itertools.cycle(iterable) - возвращает по одному значению из последов
    ...: ательности, повторенной бесконечное число раз.
    ...: 
    ...: 

In [14]: list(dropwhile(lambda x: x < 14, range(10, 20)))
Out[14]: [14, 15, 16, 17, 18, 19]

In [15]: # With dropwhile() function, we can filer sequence items until a condit
    ...: ion becomes False. 

In [16]: # itertools.dropwhile(func, iterable) - элементы iterable, начиная с пе
    ...: рвого, для которого func вернула ложь.

In [17]: # itertools.filterfalse(func, iterable) - все элементы, для которых fun
    ...: c возвращает ложь.

In [18]: [k for k, g in groupby('AAAABBBCCDAABBB')]
Out[18]: ['A', 'B', 'C', 'D', 'A', 'B']

In [19]: # itertools.groupby(iterable, key=None) - группирует элементы по значен
    ...: ию. Значение получается применением функции key к элементу (если аргуме
    ...: нт key не указан, то значением является сам элемент).

In [20]: print(*islice('ABCDEFG', 2))
A B

In [21]: # итератор из среза

...

In [23]: print(*permutations('ABC', 2))
('A', 'B') ('A', 'C') ('B', 'A') ('B', 'C') ('C', 'A') ('C', 'B')

In [24]: # перестановка

In [25]: print(*product('ABC', 'd'))
('A', 'd') ('B', 'd') ('C', 'd')

In [26]: # произведение

In [27]: print(*repeat('ABC', 2))
ABC ABC

In [28]: # повторить определенное количество раз

In [29]: print(*starmap(pow, [(2,5), (3,2), (10,3)]))
32 9 1000

In [30]: # Make an iterator that computes the function using arguments obtained 
    ...: from the iterable. 

In [31]: print(*takewhile(lambda x: x<5, [1,4,6,7,11]))
1 4

In [32]: # пока тру - возвращает данные

...

In [40]: single_iterator = islice(count(), 3)

In [41]: cloned1, cloned2 = tee(single_iterator)

In [42]: for num in cloned1:
    ...:     print('cloned1: {}'.format(num))
    ...: for num in cloned2:
    ...:     print('cloned2: {}'.format(num))
    ...:     
cloned1: 0
cloned1: 1
cloned1: 2
cloned2: 0
cloned2: 1
cloned2: 2

In [43]: # itertools.tee(iterable, n=2) - кортеж из n итераторов.

In [44]: print(*zip_longest('ABCD', 'xy', fillvalue='-'))
('A', 'x') ('B', 'y') ('C', '-') ('D', '-')
```
