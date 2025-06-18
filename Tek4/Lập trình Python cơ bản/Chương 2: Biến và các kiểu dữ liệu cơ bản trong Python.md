## 1. Gán giá trị cho biến
### 1.1 Biến không hợp lệ
- Tên biến hợp lệ chỉ gồm sự kết hợp của các chữ cái thường (a đến z) hoặc hoa (A đến Z), các chữ số (0 đến 9) và dấu gạch dưới _.
- Các tên biến không hợp lệ:
  + Chứa khoảng trắng
  + Tên bắt đầu bằng một chữ số. (vd: 1variable)
  + Tên trùng với từ khóa của Python như: global, import, break, None,...
  + Tên sử dụng ký tự đặc biệt như: !, @, #, $, % ...
### 1.2 Gán một giá trị
```
account_balance = 100
print(account_balance)
```
output: 100
### 1.3 Gán nhiều giá trị
```
a, b, c = 100, "Python", 200
print (a)
print (b)
print (c)
```
```
a = b = c = 100
print (a)
print (b)
print (c)
```
## 2. Thay đổi giá trị của biến
```
amount = 50
print(amount)

amount = 200
print(amount)
```

