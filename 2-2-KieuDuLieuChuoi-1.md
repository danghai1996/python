# Kiểu dữ liệu chuỗi trong Python (Phần 1)

## Chuỗi là gì?
Trong Python, chuỗi là những thứ được đặt trong cặp dấu `‘ ’`, hoặc `“ ”`,  có thể cũng là trong cặp  `‘’’ ‘’’`, `“”” “””`. Nhưng cơ bản và thường đường sử dụng nhất là cặp `‘ ‘` và `“ “`.

## Ví dụ về chuỗi
```py
>>> a = 'Đây là đấu ngoặc kép " '
>>> 
>>> print(a)
Đây là đấu ngoặc kép " 
```

```py
>>> b = "Đây là dấu nháy đơn '"
>>> 
>>> print(b)
Đây là dấu nháy đơn '
```

## Docstring
Để tạo chú thích, ta có thể sử dụng `#` hoặc `'''<chú thích>'''`. Hoàn toàn có thể sử dụng `"""<chú thích>"""`
```py
# ĐÂy là comment 1 dòng
# Đây cũng là comment 1 dòng
'''
Comment 
nhiều
dòng
như
thế
này
'''
```

## String Operator
1. Nhân với kiểu `str`
    ```py
    >>> mess = 'helloWorld'
    >>> print(mess * 2)
    helloWorldhelloWorld
    ```

2. Cộng string
    ```py
    a = 'Ahihi!'
    b = 'Đồ ngốc'
    print(a + b)
    ```
    OUTPUT
    ```
    Ahihi!Đồ ngốc
    ```

## Escape Sequence
- Là chuỗi kí tự đặc biệt trong Python. Bắt đầu bằng dấu `\`

|Tên|Kí hiệu|Ý nghĩa|
|---|-------|-------|
|Alert|`\a`|Phát ra 1 tiến bíp|
|Backspace|`\b`|Đưa con trỏ về lại một khoảng trắng|
|Newline|`\n`|Đưa con trỏ xuống dòng tiếp theo|
|Horizontal|`\t`|Tạo 1 khoảng tab|
|Single quote|`\'`|In ra ký tự `'`|
|Double quote|`\"`|In ra ký tự `"`|
|Backslash|`\\`|In ra ký tự `\`|

## Chuỗi trần
Đôi khi, ta gặp rắc rối với Escape Sequence như sau.

Ta muốn in ra đường dẫn ổ đĩa hệ thống dạng `Ổ_đĩa:\Thư_mục\Thư_mục` mà nó dính nhiều các ký tự `\`

Python cung cấp một dạng chuỗi là chuỗi trần với cú pháp:
```py
r'nội dung chuỗi'
```

**Lưu ý:** chuỗi trần không phải bỏ qua các Escape Sequence, mà nó sẽ giúp chúng ta sửa những Escape Sequence đó, như cách chúng ta làm
```py
>>> a = r'Ổ_đĩa:\Thư_mục\Thư_mục'
>>>
>>> print(a)
Ổ_đĩa:\Thư_mục\Thư_mục
>>> 
>>> a
'Ổ_đĩa:\\Thư_mục\\Thư_mục'
```

## Indexing chuỗi ký tự
Mặc định, khi ta lưu một chuỗi vào biến, thì các ký tự sẽ được đánh số thứ tự từ 0 -> n-1 (n : số ký tự của chuỗi)

Ví dụ: 
Ta có 1 chuỗi như sau
```py
s = 'abc xyz'
```

Thì các ký tự được đánh số như sau:
|a|b|c| |x|y|z|
|-|-|-|-|-|-|-|
|0|1|2|3|4|5|6|

Ta có thể lấy bất kỳ ký tự nào trong chuỗi này bằng cách gọi như sau:
```
s[vị trí]
```

- Lấy độ dài của chuỗi
    ```py
    len(s)
    ```

**Lưu ý:** 
- `[vị trí]` < `len(s)`
- `[vị trí]` : phải là số nguyên

**Ví dụ:**
```py
>>> s = 'abc xyz'
>>> 
>>> s[0]
'a'
>>> 
>>> s[5]
'y'
>>> s [7] # Vị trí không tồn tại
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: string index out of range
>>>
>>> len(s) # Độ dài của chuỗi là 7
7
>>> s[-1] # Nếu có dấu - thì sẽ tính từ bên phải sang trái và bắt đầu bằng 1
'z'
>>> s[-2] 
'y'
>>> s[-0]
'a'
```

## Cắt chuỗi
Để lấy 1 đoạn trong chuỗi ta sử dungj cú pháp
```py
<chuỗi>[vị trí bắt đầu : vị trí dừng]
```

**Ví dụ:**

Ta có chuỗi sau
```py
s = 'abc xyz'

# Lấy chuỗi 3 ký tự đầu
>>> s[0:3]
'abc'

>>> s[1:4]
'bc '
```

- Lấy từ 1 vị trí đến cuối chuỗi: Sử dụng `None` hoặc bỏ trống vị trí dừng
    ```py
    >>> s[2:None]
    'c xyz'

    >>> s[2:] # Bỏ trống vị trí dừng
    'c xyz'
    ```

- Lấy từ vị trí đầu đến 1 vị trí xác định: Sử dụng `None` tại vị trí bắt đầu
```py
>>> s[None:3]
'abc'

>>> s[:3] # Bỏ trống vị trí bắt đầu
'abc'
```

### Cắt chuỗi với bước nhảy
Mặc định : nếu không khai báo bước nhảy thì hệ thoogns mặc định sẽ để bước nhảy là 1.

**Cú pháp :**
```py
<chuỗi>[vị trí bắt đầu : vị trí dừng : bước nhảy]
```

**Ví dụ:** chuỗi : `s = 'abc xyz'`
- Mặc định, bước nhảy là 1:
    ```py
    >>> s[1:4]
    'bc '
    >>> s[1:4:1]
    'bc '
    ```

- Khai báo bước nhảy bằng 2
    ```py
    >>> s[1:7:2]
    'b y'
    ```

- Ta có thể điều chỉnh việc cắt từ phải sang trái bằng cách sử dụng bước nhảy âm
    ```py
    >>> s[5:1:-2] # Bắt đầu từ vị trí 5, kết thúc tại 1 và lấy tại vị trí 5, 3
    'y '
    ```

- Một lưu ý nhỏ khi các bạn đặt bước là một số âm, thì vị trí bắt đầu mà bạn để là None thì nó sẽ được đặt là n – 1(-1) với n là độ dài chuỗi. Còn với vị trí dừng thì sẽ là cắt hết trọn vẹn tới đầu chuỗi có nghĩa là vị trí dừng ở trường hợp này không phải là 0.
    ```py
    >>> s
    'abc xyz'

    >>> s[4::-1] # lấy các kí tự có vị trí từ 4 đến 0
    'x cba'

    >>> s[::-1] # lấy chuỗi ngược với bước nhảy âm
    'zyx cba'
    ```

**Lưu ý:** Không được đặt bước nhảy bằng 0

## Ép kiểu dữ liệu
Như đã biết, 2 biến a và b dưới đây là khác nhau:
```py
>>> a = '1996'
>>> b = 1996

>>> type(a) # Biến a là kiểu chuỗi ký tự string
<class 'str'>

>>> type(b) # Biến b là kiểu số nguyên interger
<class 'int'>
```

Khi thực hiện biểu thức dưới đây sẽ khác nhau:
```py
>>> a * 2
'19961996'

>>> b * 2
3992
```

Để có thể ép kiểu một chuỗi ký tự là các số thành dạng int, ta sử dụng `int()`
```py
>>> a
'1996'
>>> int(a) # Biến a sẽ trả về với giá trị là số nguyên
1996
>>> type(a) # Điều này không thay đổi kiểu dữ liệu thực của a
<class 'str'>

>>> c = 5.136
>>> int(c) # Biến c sẽ được trả về với phần nguyên
5
>>> type(c) # Kiểu dữ liệu không thay đổi
<class 'float'> 
```

Tương tự, ta có thể ép kiểu `str()` và `float()`.

**Lưu ý:** Bạn sẽ không thể chuyển đổi một số thực dưới dạng chuỗi bằng hàm `int`
```py
>>> e = '102.32'
>>> int(e)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: '102.32'
```

Để có thể làm điều đó, ta sẽ thực hiện ép kiểu 2 lần. Trong trường hợp này sẽ là:
```py
>>> e = '102.32'
>>> type(e)
<class 'str'>

>>> int(float(e)) # Ta sẽ thực hiện ép kiểu từ str -> float -> int
102
```

## Thay đổi nội dung chuỗi
Ta không thể thay đổi nội dung chuỗi bằng cách gán giá trị cho từng vị trí như các ngôn ngữ khác được
```py
>>> s = 'abc xyz'
>>> s[2] = 'd'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
```

Ta chỉ có thể thay thế nó một cách gián tiếp giá trị chuỗi mà biến của bạn lưu giữ bằng cách sử dụng việc cắt chuỗi và toán tử `+` để tạo ra một chuỗi mới và gán lại vào biến của bạn.

**Ví dụ:** Ta có chuỗi `s = 'abc xyz'`
Để thay kí tự `s[0]` từ `a` thành `h`, ta cần ghi lại cả chuỗi `s` bằng cách ghép kí tự `h` với chuỗi kí tự từ `s[1]` đến cuối.
```py
>>> s = 'abc xyz'
>>> s = 'h' + s[1::] # Sử dụng cắt chuỗi để giữ lại những phần không thay đổi
>>> s
'hbc xyz'
```