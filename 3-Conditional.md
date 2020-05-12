# Câu lệnh điều kiện

# Biểu thức Boolean
Biểu thức Boolean trả về 2 giá trị **True** hoặc **False**.

**Ví dụ:**
```py
>>> 5 == 5
True
>>> 5 == 6
False
```

**True** và **False** không phải kiểu String. Chúng là kiểu Bool
```py
>>> type(True)
<class 'bool'>
>>> type(False)
<class 'bool'>
```

Một số các phương thức để so sánh là
|Biểu thức|Ý nghĩa|
|---------|-------|
|`x != y`|x khác y|
|`x > y` |x lớn hơn y|
|`x < y`|x nhỏ hơn y| 
|`x >= y`|x lớn hơn hoặc bằng y|
|`x <= y`|x nhỏ hơn hoặc bằng y|
|`x is y`|x giống y(so sánh chuỗi)|
|`x is not y`|x không giống y(so sánh chuỗi)|

# Toán tử Logic
Có 3 toán tử logic: `and`, `or`, `not`.

Ví dụ:
```py
>>> x = 5
>>> x > 0 and x < 10
True
>>> x < 0 and x > 3
False
```

```py
>>> x = 5
>>> x < 0 or x > 3
True
>>> x < 0 or x > 10
False
```

```py
>>> x = 5
>>> not (x > 6)
True
>>> not (x > 6)
True
```

```py
>>> 17 and True
True
>>> 17 and False
False
```

# Câu lệnh điều kiện
Câu lệnh điều kiện trong Python được sử dụng với `if`

## Câu lệnh điều kiện `if`
**Câu lệnh dạng đơn giản:**
```py
if x > 0 :
    print('x is positive')
```

**Logic:**

<img src="https://i.imgur.com/W6xillx.png">

**Một số quy tắc:**
- Sau điều kiện là dấu 2 chấm `:`

- Phần thực thi phải có ít nhất một câu lệnh.

- Dưới `if`, các câu lệnh thụt lề
    ```py
    if <điều kiện> : 
        câu lệnh 1
        câu lệnh 2
        ...
    ```

- Để giữ chỗ và tránh lỗi khi chưa có câu lệnh trong `if`, ta có thể sử dụng lệnh `pass`
    ```py
    if x < 0 :
        pass  
    ```

## Câu lệnh rẽ nhánh `if ... else`
Xét ví dụ:
```py
if x%2 == 0 :
    print('x is even')
else :
    print('x is odd')
```

**Logic**

<img src="https://i.imgur.com/GwiVaFC.png">

## Rẽ nhánh `if...elif...else`
Ví dụ:
```py
if x < y:
    print('x is less than y')
elif x > y:
    print('x is greater than y')
else:
    print('x and y are equal')
```

**Logic:**

<img src="https://i.imgur.com/Dh4CHRm.png">

**Lưu ý:**
- Không có giới hạn số lần `elif`

- Nếu có `else` thì nó phải ở cuối, nhưng không cần phải có một mệnh đề

```py
if choice == 'a':
    print('Bad guess')
elif choice == 'b':
    print('Good guess')
elif choice == 'c':
    print('Close, but not correct')
```

## Câu lệnh điều kiện lồng nhau (`if` lồng)
Một điều kiện cũng có thể được lồng trong một cái khác. Chúng ta có thể đã viết ví dụ ba nhánh như thế này:
```py
if x == y:
    print('x and y are equal')
else:
    if x < y:
        print('x is less than y')
    else:
        print('x is greater than y')
```

**Logic:**

<img src="https://i.imgur.com/H2Qsb2U.png">

Tuy nhiên, ta có thể sử dụng các toán tử logic để có thể ghép các điều kiện trong các trường hợp nhất định

Ví dụ: Đoạn điều kiện dưới đây
```py
if 0 < x:
    if x < 10:
        print('x is a positive single-digit number.')
```
Ta có thể viết ngắn gọn lại như sau:
```py
if 0 < x and x < 10:
    print('x is a positive single-digit number.')
```

# `Try - except` để bắt ngoại lệ 
## Cách hoạt động `try - except`
