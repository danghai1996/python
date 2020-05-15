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
**Ví dụ:** chương trình đổi nhiệt độ từ F sang C
```py
inp = input('Enter Fahrenheit Temperature: ')
fahr = float(inp)
cel = (fahr - 32.0) * 5.0 / 9.0
print(cel)
```

Khi nhập đúng input:
```py
Enter Fahrenheit Temperature: 50
10.0
```

Khi nhập sai sẽ nhận được thông báo lỗi 
```py
Enter Fahrenheit Temperature: ah
Traceback (most recent call last):
  File "/home/haidd/python/python.py", line 2, in <module>
    fahr = float(inp)
ValueError: could not convert string to float: 'ah'
```

Khi đó, ta nên sử dụng `try-except` để tránh trường hợp nhập sai sẽ bị dừng chương trình
```py
inp = input('Enter Fahrenheit Temperature:')
try:
    fahr = float(inp)
    cel = (fahr - 32.0) * 5.0 / 9.0
    print(cel)
except:
    print('Please enter a number')
```

Khi nhập đúng:
```py
Enter Fahrenheit Temperature:78.256
25.697777777777777
```

Khi nhập sai:
```py
Enter Fahrenheit Temperature:danghai1996
Please enter a number
```

# Bài tập
## Bài 1: 
Viết chương trình tính lương cho nhân viên với điều kiện:
Lương theo giờ được nhân 1.5 bắt đầu từ giờ 41 trở đi.

**INPUT:**
- Số giờ làm : số nguyên
- Lương 1 giờ : số nguyên

**OUTPUT:**
- Lương theo giờ

**File Code:**
```py
hour = int(input('Nhập số giờ làm: '))
rate = int(input('Nhập hệ số lương/1 giờ: '))
sal = 0

if hour < 0:
    print('Số giờ làm phải là số nguyên dương !')
elif hour <= 40:
    sal = float(hour * rate)
elif hour > 40:
    sal = float(40 * rate + (hour - 40) * rate * 1.5)

print('Lương của nhân viên với {0} giờ làm là: {1}'.format(hour, rate))  
```

**Run**
```py
Nhập số giờ làm: 30
Nhập lương 1 giờ: 10
Lương của nhân viên với 30 giờ làm là: 300
----
Nhập số giờ làm: 45
Nhập lương 1 giờ: 10
Lương của nhân viên với 45 giờ làm là: 475.0
```

## Bài 2:
Chỉnh lại bài 1 bắt điều kiện nhập sai kiểu dữ liệu đầu vào với `try..exept`

**Code**
```py
hour = input('Nhập số giờ làm: ')
rate = input('Nhập hệ số lương/1 giờ: ')
sal = 0
try:
    hour = int(hour)
    rate = int(rate)
    sal = float(sal)
    if hour < 0:
        print('Số giờ làm phải là số nguyên dương !')
    elif hour <= 40:
        sal = hour * rate
    elif hour > 40:
        sal = 40 * rate + (hour - 40) * rate * 1.5

    print('Lương của nhân viên với {0} giờ làm là: {1}'.format(hour, sal))  
except:
    print('Hãy nhập số nguyên dương cho Số giờ làm và Hệ số lương')
```

**Run**
```py
Nhập số giờ làm: ten 
Nhập hệ số lương/1 giờ: 10
Hãy nhập số nguyên dương cho Số giờ làm và Hệ số lương
----
Nhập số giờ làm: 10
Nhập hệ số lương/1 giờ: ten
Hãy nhập số nguyên dương cho Số giờ làm và Hệ số lương
----
Nhập số giờ làm: ten
Nhập hệ số lương/1 giờ: ten
Hãy nhập số nguyên dương cho Số giờ làm và Hệ số lương
----
Nhập số giờ làm: 40
Nhập hệ số lương/1 giờ: 10
Lương của nhân viên với 40 giờ làm là: 400
----
Nhập số giờ làm: 45
Nhập hệ số lương/1 giờ: 10
Lương của nhân viên với 45 giờ làm là: 475.0
```

## Bài 3:
**INPUT**
- Một số trong khoảng 0.0 đến 0.1

**Điều kiện OUTPUT**
```
Score   Grade
>= 0.9     A
>= 0.8     B
>= 0.7     C
>= 0.6     D
 < 0.6     F
```

**Code**
```py
score = input('Nhập điểm trong khoảng 0.0 đến 1.0: ')

try:
    score = float(score)
    if score < 0 or score > 1 :
        print('Bad score')
    elif score < 0.6 :
        print('F')
    elif score < 0.7 :
        print('D')
    elif score < 0.8 :
        print('C')
    elif score < 0.9 :
        print('B')
    else:
        print('A')
except:
    print('Bad score')
```

**Run**
```py
Nhập điểm trong khoảng 0.0 đến 1.0: -1
Bad score
----
Nhập điểm trong khoảng 0.0 đến 1.0: -.2
Bad score
----
Nhập điểm trong khoảng 0.0 đến 1.0: 0.2
F
----
Nhập điểm trong khoảng 0.0 đến 1.0: .3
F
----
Nhập điểm trong khoảng 0.0 đến 1.0: .6
D
----
Nhập điểm trong khoảng 0.0 đến 1.0: .7
C
----
Nhập điểm trong khoảng 0.0 đến 1.0: .8
B
----
Nhập điểm trong khoảng 0.0 đến 1.0: .9
A
----
Nhập điểm trong khoảng 0.0 đến 1.0: 1
A
```

## Bài 4:
Tìm số lớn nhất trong 3 số.
```py
a = input('a = ')
b = input('b = ')
c = input('c = ')

try:
    a = float(a)
    b = float(b)
    c = float(c)
    max = a
    if b > max :
        max = b
        if c > max :
            max = c
    elif c > max:
        max = c
    print(max)
except:
    print('a, b, c phải là kiểu số !!!')
```