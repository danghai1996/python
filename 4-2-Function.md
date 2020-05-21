# Function - Một số bài tập tự luyện

## Bài 1:
Viết lại hàm tính toán lương cho nhân viên với đầu vào là số giờ và hệ số lương.

Code
```py
def compute_pay(hour, rate):
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

        print("Hours : {0}".format(hour))
        print("Rate : {0}".format(rate))
        print("Sal : {0}".format(sal))
    except:
        print('Hãy nhập số nguyên dương cho Số giờ làm và Hệ số lương')
#----------------------------------------------#
hour = int(input("Enter hour : "))
rate = int(input("Enter rate : "))
compute_pay(hour, rate)
```
OUTPUT
```
Enter hour : 45
Enter rate : 10
Hours : 45
Rate : 10
Sal : 475.0
```

## Bài 2:
Viết lại hàm nhập điểm số sẽ in ra điểm bằng chữ.
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
def computegrade(score):
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
#----------------------------------------------------#
score = input('Nhập điểm trong khoảng 0.0 đến 1.0: ')
computegrade(score)
```