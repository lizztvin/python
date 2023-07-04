![image](https://github.com/lizztvin/python/assets/74359143/2880a408-d026-4b31-80cc-c492e50fab92)
```python
def main(a):
    a = a.replace('\n', '')
    a = a.replace('|', '')
    a = a.replace('var', '')
    a = a.replace('`', '')
    a = a.replace('(', '')
    a = a.replace(')', '')
    a = a.replace("'", "")
    a = a.replace('.', '')
    a = a.replace(' ', '')
    a = a.split('@')
    a.pop(0)
    for i in range(len(a)):
        a[i] = a[i].split('<#')
        a[i][1] = a[i][1].split(',')
    return dict(a)

```
