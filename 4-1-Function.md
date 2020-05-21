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
- Chương trình sẽ chạy lượt lượt các câu lệnh từ trên xuống dưới.

- Khi gọi đến một hàm, nó sẽ gọi đến các câu lệnh của hàm đó và thực hiện lượt lượt các câu lệnh của hàm đó sau đó sẽ thoát hàm và tiếp tục các câu lệnh của chương trình.

- Việc hàm trong hàm cũng tương tự.

## Tham số và đối số (Parametters và Arguments)
Một số hàm dựng sẵn yêu cầu đối số. Có thể có một hoặc nhiều đối số.

Bên trong hàm, các đối số được gán cho biến được gọi là các tham số.

**Ví dụ:**
```py
def say_hello(name):
    print("Hello {0}".format(name))

say_hello("Hải")
```
OUTPUT
```
Hello Hải
```

Sử dụng với các toán tử.

**Ví dụ:**
```py
import math
def print_spam(spam):
    print(spam)

print_spam('spam ' * 4)

print_spam(math.cos(math.pi))
```
OUTPUT
```
spam spam spam spam 
-1.0
```

## Fruitful functions và void functions (Hàm trả về giá trị và hàm thực hiện lệnh không trả về kết quả)

Khi ta gọi một Fruitful functions, ta có thể sử dụng nó để gán giá trị cho biến hoặc sử dụng nó trực tiếp trong biểu thức

**Ví dụ:**
```py
import math

x = math.cos(90)

y = math.sqrt(4) + 1

print("x = {0}".format(x))
print("y = {0}".format(y))
```
**OUTPUT**
```
x = -0.4480736161291701
y = 3.0
```

Void functions có in ra màn hình, nhưng nếu ta gán kết quả của nó cho một biến, ta sẽ nhận được một giá trị đặc biệt là `None`

```py
def say_hello(name):
    print("Hello {0}".format(name))

x = say_hello('Hải')
print(x)
```
OUTPUT
```
Hello Hải
None
```

Để trả về kết quả từ một hàm, ta sử dụng `return`.

**Ví dụ:** Hàm tính tổng 2 số
```py
def addtwo(a, b):
    sum = a + b
    return sum

s = addtwo(5, 6)

print(s)
```
OUTPUT
```
11
```

## Tại sao phải dùng Functions
- Việc tạo functions sẽ giúp bạn nhóm các câu lệnh với nhau. Giúp chương trình dễ đọc, dễ hiểu và dễ debug hơn

- Các functions sẽ giúp chương trình gọn hơn bằng cách không phải sử dụng các lệnh lặp đi lặp lại nhiều lần.

- Khi muốn sửa một chức năng gồm nhiều câu lệnh sẽ chỉ phải sửa tại hàm.

- Một functions tốt có thế sử dụng được ở nhiều chương trình. Khi bạn sử dụng và debug sẽ đơn giản hơn