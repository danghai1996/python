# Kiểu dữ liệu chuỗi trong Python (Phần 2)

## Định dạng bằng toán tử `%`
Ví dụ đơn giản:
```py
>>> 'Ahihi ! %s' %('Đồ ngốc')
'Ahihi ! Đồ ngốc'

>>> '%d. Đây là số %s' %(1, 'một')
'1. Đây là số một'
```

### Cú pháp
```py
<chuỗi> % (giá trị thứ 1, giá trị thứ 2, .., giá trị thứ n – 1, giá trị thứ n)
```

### Sử dụng với biến
Ví dụ:
```py
>>> a = 'Đồ ngốc'
>>> 'Ahihi ! %s' %(a)
'Ahihi ! Đồ ngốc'

>>> a = 1
>>> b = 'một'
>>> s = '%d. Đây là số %s' %(a, b)
>>> s
'1. Đây là số một'
```

### Các loại toán tử thường dùng
|Toán tử|Giải thích|
|-------|----------|
|`%s`|Giá trị dạng string (`str`)|
|`%d`|Giá trị kiểu số nguyên (`int`). Nếu là số thực thì chỉ hiển thị phần nguyên|
|`%<số chữ số thập phân>f`|Giá trị kiểu số thực|
|`%r`|Giá trị kiểu `repr`|


## Định dạng bằng chuỗi f (f-string)
Phương pháp định dạng này cho bạn khả năng thay thế một số chỗ ở trong một chuỗi bằng  giá trị của các biến mà bạn đã khởi tạo và có. Và để có thể sử dụng cách này, bạn phải có một chuỗi f.

### Cú pháp
```py
f ’<giá trị trong chuỗi>’
```

### Cách sử dụng
Ví dụ 1:
```py
>>> tx = 'strings'
>>> f'This is a {tx}.'
'This is a strings.'
```

Ví dụ 2:
Nếu muốn hiển thị 1 chuỗi nội dung sau:
```
1: {one}, 2: {two}, 3: {variable}
```
Ta chỉ muốn thay giá trị tại `variable` thành `three`. Ta sẽ thực hiện thêm `{}` vào các vị trí `{one}` và `{two}`.
```py
>>> variable = ‘three’
>>> f'1: {{one}}, 2: {{two}}, 3: {variable}'
'1: {one}, 2: {two}, 3: three'
```

## Định dạng bằng phương thức format
Cách định dạng này cho phép Python định dạng chuỗi một cách tuyệt vời, không chỉ tốt về mặt nội dung mà còn về thẩm mĩ. Định dạng bằng phương thức format

```py
>>> 'a: {}, b: {}, c: {}'.format(1, 2, 3)
'a: 1, b: 2, c: 3'
```

Nếu chỉ như vậy, thì nó không có gì khác biệt với sử dụng toán từ `%`. Sự khác biệt như sau:
```py
>>> 'a: {1}, b: {2}, c: {0}'.format('one', 'two', 'three')
'a: two, b: three, c: one'
```

Việc đánh số thứ tự các biến sẽ giúp ta linh hoạt trong việc sử dụng các giá trị, cũng như nếu dư giá trị cũng không có vấn đề gì
```py
# Thừa giá trị cũng không xảy ra lỗi
>>> 'a: {1}, b: {2}, c: {0}'.format('one', 'two', 'three', 'four')
'a: two, b: three, c: one'

# Có thể sử dụng 1 giá trị nhiều lần mà không cần thêm
>>> 'a: {1}, b: {0}, c: {0}'.format('one', 'two', 'three', 'four')
'a: two, b: one, c: one'
```

Bạn hoàn toàn có thể đặt tên biến và giá trị cho các vị trí để có thể dễ nhớ và tránh nhầm lẫn. Ví dụ
```py
>>> 'a: {one}, b: {two}, c: {three}'.format(one = 111, two = 222, three = 333)
'a: 111, b: 222, c: 333'
```

### Định dạng, căn lề với phương thức Format
3 cách căn lề cơ bản của phương thức format

|Mô tả|Format|
|-|-|
|Căn lề trái|`{:(c)<n}`|
|Căn lề phải|`{:(c)>n}`|
|Căn giữa|`{:(c)^n}`|

**Trong đó:**
- `c` : là ký tự bạn muốn thay thế vào chỗ trống, nếu để trống thì sẽ là ký tự khoảng trắng
- `n` : số ký tự dùng để căn lề

Ví dụ: Theo dõi các trường hợp dưới đây để hiểu rõ hơn
```py
>>> '{:^10}'.format('1234') # Căn giữa
'   1234   '

>>> '{:>10}'.format('1234') # Căn lề phải
'      1234'

>>> '{:<10}'.format('1234') # Căn lề trái
'1234      '

>>> '{:*^10}'.format('1234') # Căn giữa, thay khoảng trắng thành dấu *
'***1234***'

>>> '{:*<10}'.format('1234') # Căn lề trái với dấu *
'1234******'

>>> '{:*>10}'.format('1234') # Căn lề phải với dấu *
'******1234'
```

**Ví dụ:** cách sử dụng với file python

Tạo file Python:
```py
# phần định dạng
row_1 = '+ {:-<6} + {:-^15} + {:->10} +'.format('', '', '')
row_2 = '| {:<6} | {:^15} | {:>10} |'.format('ID', 'Họ và tên', 'Nơi sinh')
row_3 = '| {:<6} | {:^15} | {:>10} |'.format('1', 'Đặng Đỗ Hải', 'Hưng Yên')
row_4 = '| {:<6} | {:^15} | {:>10} |'.format('2', 'Hải Đặng', 'Hà Nội')
row_5 = '+ {:-<6} + {:-^15} + {:->10} +'.format('', '', '')

# phần xuất kết quả
print(row_1)
print(row_2)
print(row_3)
print(row_4)
print(row_5)
```

Run file ta được kết quả như sau:
```
+ ------ + --------------- + ---------- +
| ID     |    Họ và tên    |   Nơi sinh |
| 1      |   Đặng Đỗ Hải   |   Hưng Yên |
| 2      |    Hải Đặng     |     Hà Nội |
+ ------ + --------------- + ---------- +
```

