# Variables, expressions, and statements (Biến, biểu thức và câu lệnh)

## Values and types (Giá trị và kiểu dữ liệu)
- Integers (`int`) : số nguyên
    ```python
    print(2)
    ```

- String (`str`)
    ```python
    print("Hello World!")
    print('Hello World!')
    ```

- Float (`float`) : số thập phân
    ```py
    print(1.5)
    ```

- Muốn kiểm tra kiểu dữ liệu, ta có thể sử dụng trình thông dịch như sau:
    ```python
    >>> type(4)
    <class 'int'>
    >>> 
    >>> type("Hello World!")
    <class 'str'>
    >>> 
    >>> type('Hello World!')
    <class 'str'>
    ```

- Có thể in nhiều số như sau:
    ```py
    >>> print(1,000,000)
    1 0 0

    >>> print(1,000,000)
    1 0 0
    ```


## Variable (biến)
Một trong những tính năng mạnh mẽ nhất của ngôn ngữ lập trình là khả năng thao tác các biến. Một biến là một tên đề cập đến một giá trị.

- Gán giá trị cho biến bằng dấu `=`
    ```py
    message = "Hello Python!"
    n = 2020
    pi = 3.1415926535897931
    ```

- Gán giá trị nhiều biến
    ```py
    message = "Hello Python!", n = 2020, pi = 3.1415926535897931
    ```

- Cách sử dụng biến với `print`
    ```py
    >>> print(message)
    Hello World!

    >>> print(n)
    2020

    >>> print(pi)
    3.141592653589793
    ```

- Kiểm tra kiểu dữ liệu của các biến ta vừa đặt
    ```py
    >>> type(message)
    <class 'str'>

    >>> type(n)
    <class 'int'>

    >>> type(pi)
    <class 'float'>
    ```

## Variable names and keywords
### Quy tắc đặt tên biến
- Biến có thể chứa cả chữ và số
- Biến không thể bắt đầu bằng số
- Nên đặt tên biến bắt đầu bằng chữ thường và sử dụng dấu gạch dưới `_`. Ví dụ: `name_variable`, `number_of_variable`, ...

Python có 35 keywords không được sử dụng để đặt tên biến:
```
and       del       from      None      True
as        elif      global    nonlocal  try
assert    else      if        not       while
break     except    import    or        with
class     False     in        pass      yield
continue  finally   is        raise     async
def       for       lambda    return    await
```

## Statements (Các câu lệnh)
Một tập các câu lệnh sẽ thực hiện lần lượt khi được chạy từ file hoặc theo các điều kiện đã được đặt ra.

Ví dụ:
```py
print(1)
x = 2
print(x)
```

OUTPUT
```
1
2
```


## Nhập dữ liệu từ bàn phím
Để yêu cầu người dùng nhập giá trị từ bàn phím. Ta sử dụng lệnh `input`
```py
name = input('What your name? : ')
print('My name is ' + name)
```
OUTPUT
```
What your name? : Hải
My name is Hải
```

Để định dạng kiểu dữ liệu nhập vào:
```py
name = int(input())
print(name + 5)
```

OUTPUT
```
10
15
```
