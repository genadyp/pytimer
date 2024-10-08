# pytimer

### API

```python
# timer.py

class Timer:
  def __init__(self, tag: str = None): ...
  def start(self): ...
  def stop(self): ...
  def reset(self): ...
  def pause(self): ...
  def resume(self): ...
  def elapsed(self) -> datetime.timedelta: ...

  @property
  def tag(self) -> Optional[str]: ... 

  def __enter__(self): ...
  def __exit__(self, exc_type, exc_value, exc_tb): ...

# timers.py

_timers = dict()

def add_timer(tag: str, raise_if_exist: bool = True) -> Timer: ...

def get_timer(tag: str, add_if_absent: bool = False) -> Timer: ...

def destroy_timer(tag: str, raise_if_absent: bool = True) -> Timer: ...

__all__ = ["add_timer", "get_timer", "destroy_timer"]

# decorators.py

def get_stat(...):
  """return collected statistics"""
  ...

def collect(...):
  """collect execution time of the wrapped method"""
  ...
```

### Inspirations

https://docs.python.org/3/library/timeit.html

https://github.com/ramonsaraiva/timy


