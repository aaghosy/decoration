# decoration
装饰器在Python中是一种高级的函数修改和增强技术。它允许你在不改变原始函数定义的情况下，为函数添加新的功能。装饰器本质上是一个函数，它接收另一个函数作为参数，并返回一个新的函数。

### 基本原理

- 装饰器是可调用的对象（通常是函数），它接受一个函数作为参数，并返回另一个函数。
- 它用于在不改变原始函数代码的前提下，给函数添加新的功能，如日志记录、性能测试、权限验证等。

### 示例代码

下面是一个简单的装饰器示例，该装饰器用于记录函数的调用信息：

```python
def my_decorator(func):
    def wrapper(*args, **kwargs):
        print(f"Function {func.__name__} is called with arguments {args} and {kwargs}")
        result = func(*args, **kwargs)
        print(f"Function {func.__name__} returned {result}")
        return result
    return wrapper

# 使用装饰器
@my_decorator
def add(a, b):
    return a + b

# 调用函数
result = add(3, 4)
```

在这个例子中：
- `my_decorator`是一个装饰器。它在被装饰的函数（`add`）执行前后打印信息。
- 使用`@my_decorator`语法，我们将这个装饰器应用于`add`函数。
- 当调用`add`函数时，实际上是在调用由`my_decorator`返回的`wrapper`函数。

装饰器提供了一种强大且优雅的方式来修改和增强函数的行为，它让代码更加模块化和易于维护。
