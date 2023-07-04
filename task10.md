![image](https://github.com/lizztvin/python/assets/74359143/bf123c47-33e7-4565-becb-9b18ab5f58be)
```python
class MealyError(Exception):
    pass


class StateMachine:
    def __init__(self):
        self.state = 'A'

    def tweak(self):
        if self.state == 'A':
            self.state = 'A'
            return 1
        if self.state == 'B':
            self.state = 'C'
            return 2
        if self.state == 'C':
            self.state = 'D'
            return 3
        if self.state == 'D':
            self.state = 'B'
            return 6
        raise MealyError('tweak')

    def skew(self):
        if self.state == 'A':
            self.state = 'B'
            return 0
        if self.state == 'D':
            self.state = 'E'
            return 5
        if self.state == 'E':
            self.state = 'F'
            return 7
        if self.state == 'F':
            self.state = 'A'
            return 8
        raise MealyError('skew')

    def step(self):
        if self.state == 'C':
            self.state = 'F'
            return 4
        raise MealyError('step')


def main():
    return StateMachine()


def raises(func, error):
    output = None
    try:
        output = func()
    except Exception as e:
        assert type(e) == error
    assert output is None


def test():
    o = main()
    assert o.tweak() == 1
    assert o.skew() == 0
    assert o.tweak() == 2
    assert o.tweak() == 3
    assert o.tweak() == 6
    assert o.tweak() == 2
    assert o.tweak() == 3
    assert o.skew() == 5
    assert o.skew() == 7
    assert o.skew() == 8
    raises(lambda: o.step(), MealyError)
    assert o.skew() == 0
    raises(lambda: o.skew(), MealyError)
    assert o.tweak() == 2
    assert o.step() == 4
    raises(lambda: o.tweak(), MealyError)

```
