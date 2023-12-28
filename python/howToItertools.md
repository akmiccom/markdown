---
Title : How to itertools
Category : Python
Author : Makoto Yaguchi
---

# How to itertools

[TOC]

## itertools の組合せイテレータ

```Python
import itertools

# デカルト積
count = 0
for i, j in itertools.product('ABCD', repeat=2):
    print(f'{i}{j}', end=', ')
    count += 1
print(f'product : {count}')

# 重複なしのあらゆる並び
count = 0
for i, j in itertools.permutations('ABCD', 2):
    print(f'{i}{j}', end=', ')
    count += 1
print(f'permutations : {count}')

# ソートされた順で重複なし
count = 0
for i, j in itertools.combinations('ABCD', 2):
    print(f'{i}{j}', end=', ')
    count += 1
print(f'combinations : {count}')

# ソートされた順で重複あり
count = 0
for i, j in itertools.combinations_with_replacement('ABCD', 2):
    print(f'{i}{j}', end=', ')
    count += 1
print(f'combinations_with_replacement : {count}')
```

