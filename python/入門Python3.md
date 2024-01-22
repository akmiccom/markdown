---
Title : 入門Python3
Category : Python
Author : Makoto Yaguchi
---

# 入門Python3

## 1.13 復習問題

### Python のインストール
- Python のバージョンのチェック
```PowerShell
python -V
# Python 3.10.9 # デフォルトのPython version が表示される
```
- 標準Python のインストール
    - Win, Mac, Linux/Unix
- pip パッケージマネージャ
- venv 仮想環境

## 2-13 復習問題
- 変数
- 型

```Python
prince = 99
print(prince)
print(type(5)) 
print(type(3.0)) 
print(type(5 + 2.0)) 
```

## 3.6 復習問題
- 1時間は何秒か
- 変数代入
- 1日は何秒か
- 変数代入
- 浮動小数点除算
- 整数除算
```Python
second_per_hour = 60 * 60
print(f'1時間は何秒か? → {second_per_hour} sec')
second_per_day = second_per_hour * 24
print(f'1日は何秒か? → {second_per_day} sec')
print(second_per_day / second_per_hour)
print(second_per_day // second_per_hour)
``` 