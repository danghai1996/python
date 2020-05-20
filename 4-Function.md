# Function

## Gọi Function
Trong lập trình, Function là một hàm gồm 1 chuỗi các câu lệnh được đặt tên để thực hiện tính toán.

**Ví dụ gọi hàm:**
```py
>>> type(32)
<class 'int'>
```
- Tên hàm: `type`
- `32` : được gọi là đối số
- Đối số là một giá trị hoặc biến mà chúng ta đang truyền vào hàm làm đầu vào cho hàm. Kết quả hiển thị đối với hàm `type` là kiểu dữ liệu của đối số.

## Hàm tích hợp sẵn
Python xây dựng một số hàm hay sử dụng cho người dùng sử dụng trực tiếp mà không cần định nghĩa hàm.

**Ví dụ:** Hàm `max` và `min` được định sẵn trong python cho ta biết giá trị lớn nhất, nhỏ nhất trong một danh sách
```py
>>> max('Hello world')
'w'
>>> min('Hello world')
' '
```

## Hàm ép kiểu
`int`
```py
>>> int('32')
32
>>> int('Hello')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: 'Hello'
```

`float`
```py
>>> float('3.12312312')
3.12312312
>>> float('3.0')
3.0
```

`str`
```py
>>> str(32)
'32'
>>> str(3.124151)
'3.124151'
```

## Các hàm toán học
Python cung cấp một module toán học là `math` chứa hầu hết các hàm toán học quen thuộc.

Để sử dụng, ta cần `import` nó.

```py
import math
```

Để gọi một hàm trong module math, ta chỉ cần gọi như sau:
```py
math.<tên_hàm>(<đối_số>)
```

**Ví dụ:** tính sin của góc 0 độ
```py
import math
x = math.sin(0)
print(x)
```
**Output**
```py
0.0
```

Ngoài ra, một số hằng số toán học cũng được định sẵn như : số pi
```py
import math
print(math.pi)
```
Output
```
3.141592653589793
```

## Hàm random số
Ví dụ: Random số từ 1-10
```py
import random

x = random.randrange(1,10)
print(x)
```


Hay random trong một list:
```py
import random

t = [1, 3, 5, 7]
x = random.choice(t)
print(x)
```

## Tạo hàm mới
Khai báo hàm:
```py
def tên_hàm(<các đối số>):
    câu_lệnh_1
    câu_lệnh_2
    ...
```

**Quy tắc đặt tên hàm:** 
- chữ cái, số và một số dấu chấm câu là hợp pháp, nhưng ký tự đầu tiên không thể là một số
- Không thể sử dụng keyword làm tên hàm hoặc tên một hàm đã tồn tại.

**Ví dụ:**
```py
def hello():
    print("Hello world")

hello()
```
Output
```
Hello world
```

### Kiểm tra tên hàm
```py
>>> def hello():
...     print("Hello world")
... 
>>> print(hello)
<function hello at 0x7f2c55819c80>
>>> print(type(hello))
<class 'function'>
```

Bạn hoàn toàn có thể sử dụng một hàm đã định nghĩa trong một hàm khác.

## Luồng thực hiện
