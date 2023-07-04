# python
![image](https://github.com/lizztvin/python/assets/74359143/3a24132f-b9b4-4f4e-9e11-f500174d32fc)
```python
def main(a):
    res = int(a['T6']) << 26 | int(a['T5']) << 25 | int(a['T4']) << 17 |\
        int(a['T3']) << 7 | int(a['T2']) << 3 | int(a['T1']) << 0
    return str(hex(res))

```

![image](https://github.com/lizztvin/python/assets/74359143/0b510f1b-1c30-4ac6-9ae0-ae6049e225f2)
```python
def main(a):
    A1 = (a >> 0) & 0b111111111
    A2 = (a >> 9) & 0b111111111
    A3 = (a >> 18) & 0b11
    A4 = (a >> 20) & 0b11
    A5 = (a >> 22) & 0b111111
    A6 = (a >> 28) & 0b1111111111
    return [('A2', hex(A2)), ('A3', hex(A3)),
            ('A4', hex(A4)),  ('A5', hex(A5)), ('A6', hex(A6))]

```
