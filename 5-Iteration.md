# Iteration

## Update variable
Thông thường, ta sẽ update giá trị biến như sau:
```py
x = x + 1
```

Trong Python, nó sẽ đánh giá vế bên phải của biểu thức trước. Vì vậy, nếu x chưa có giá trị, sẽ báo lỗi.

```py
x = x + 1
print(x)
```
OUTPUT
```
NameError: name 'x' is not defined
```

Vì vậy, trước khi cập nhật một biến, hãy đảm bảo nó đã có giá trị
```py
x = 0
x = x + 1
print(x)
```
OUTPUT
```
1
```

## Vòng lặp `while`
**Ví dụ:** đếm ngược từ 5 về 0 và in ra chữ `Hello!`

```py
n = 5
while n > 0:
    print(n)
    n = n - 1
print('Hello!')
```

OUTPUT
```
5
4
3
2
1
Hello!
```

## Vòng lặp vô hạn (Infinite loops)
Ví dụ:
```py
n = 10
while True:
    print(n, end=' ')
    n = n - 1
print('Done!')
```

Để tránh trường hợp vào vòng lặp vô hạn, ta cần xét đúng điều kiện và có thể dùng `break` khi đến một giá trị nào đó

**Ví dụ:** dưới đây sẽ yêu cầu nhập giá trị cho biến `line` liên tục cho đến khi `line` nhận giá trị `done`.

Điều kiện là `true` nên vòng lặp luôn đúng cho đến khi gặp `break`
```py
while True:
    line = input('> ')
    if line == 'done':
        break
    print(line)
print('Done!')
```
OUPUT
```
> 

> 

> gh
gh
> done
Done!
```

## Câu lệnh `continue`
Khi sử dụng `continue` thì vòng lặp hiện tại sẽ dừng và chuyển sang vòng lặp tiếp theo mà không thực hiện các câu lệnh dưới.

**Ví dụ:** Đoạn code dưới đây sẽ thực hiện yêu cầu nhập nội dung vào, nếu bạn nhập `#` vào thì sẽ không thực hiện in ra mà sẽ tiếp tục vòng lặp yêu cầu nhập tiếp

```py
while True:
    line = input('> ')
    if line[0] == '#':
        continue
    if line == 'done':
        break
    print(line)
print('Done!')
```
OUTPUT
```
> ahihi
ahihi
> #
> #
> done
Done!
```

## Vòng lặp `for`
Ví dụ
```py
friends = ['Joseph', 'Glenn', 'Sally']
for friend in friends:
    print('Happy New Year:', friend)
print('Done!')
```
OUTPUT
```
Happy New Year: Joseph
Happy New Year: Glenn
Happy New Year: Sally
Done!
```

Với ví dụ trên, ta có thể sử dụng biến là `friend` để gọi các thành phần trong danh sách `friends` đó ra. Trong mỗi vòng lặp
```py
friends = ['Joseph', 'Glenn', 'Sally']

for friend in friends:
    print('Happy New Year:', friend)
```
OUTPUT
```
Happy New Year: Joseph
Happy New Year: Glenn
Happy New Year: Sally
```

## Mô hình vòng lặp (Loop patterns)
Thông thường, vòng lặp ta sử dụng để đi qua các danh sách các mục hoặc nội dung của tệp và tìm kiếm thứ gì đó như là giá trị lớn nhất hay giá trị nhỏ nhất.

Các vòng lặp thường được xây dựng như sau:
- Khởi tạo một hay nhiều biến trước khi vòng lặp bắt đầu
- Thực hiện tính toán trên mỗi mục trong vòng lặp, có thể thay đôi các biến trong vòng lặp.
- Nhìn vào các kết quả của biến khi vòng lặp kết thúc

## Đếm và vòng lặp
**Ví dụ:** Đếm số lượng phần tử trong list
```py
count = 0
for itervar in [3, 41, 12, 9, 74, 15]:
    count = count + 1
print('Count: ', count)
```
OUTPUT
```
Count:  6
```

**Ví dụ:** Tính tổng các giá trị trong list
```py
total = 0
for interval in [3, 41, 51, 8, 10, 6]:
    total = total + interval
print('Total: %d', total)
```
OUTPUT
```
Total:  119
```

## 