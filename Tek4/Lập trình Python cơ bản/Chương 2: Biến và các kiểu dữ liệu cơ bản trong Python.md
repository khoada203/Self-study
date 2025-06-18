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
### 1.4 Thay đổi giá trị của biến
```
amount = 50
print(amount)

amount = 200
print(amount)
```
## 2. Chuỗi ký tự trong python
- Một chuỗi ký tự hay String là một tập hợp các ký tự (chữ, số, ký tự đặc biệt như !, @,#...) kết hợp với nhau.
- Các ký tự kết hợp với nhau và nằm trong một cặp dấu nháy đơn '' hoặc nháy kép "" được gọi là một chuỗi ký tự.

### 2.1 Nối giữa hai hoặc nhiều chuỗi ký tự
- Sử dụng toán tử dấu +
```
a = 'Python'
b = 'Javascript'
print(a + b)
```
output: PythonJavascript

- Toán tử dấu hoa thị có thể được sử dụng để lặp lại chuỗi ký tự trong một số lần nhất định.
```
a = 'Python'
print(a * 4)
```
output: PythonPythonPythonPython

### 2.2 Tạo chuỗi ký tự
```
print("Hello, TEK4.VN")
print('Hello, TEK4.VN')
print('''Hello, TEK4.VN''')
print("""Hello, TEK4.VN""")
```

### 2.3 SyntaxError và NameError
- SyntaxError: chỉ các lỗi sai chính tả, soạn thảo hoặc các lỗi do dùng sai cú pháp chẳng hạn như thiếu dấu, mở hoặc đóng cặp dấu nhưng không đủ cặp,...
- NameError: xuất hiện khi trình thông dịch thấy một từ mà nó không hiểu hay không nhận ra. Trong mã nguồn chứa một số đoạn ký tự nhìn như một tên biến nhưng chưa bao giờ được định nghĩa và gán giá trị trước đó sẽ sinh ra các lỗi NameError.

## 3. Input
- Cú pháp: input([prompt])
```
a = input('Nhập một số nguyên: ')
print(a)
```
### 4. Chatbot đơn giản nhại lại người dùng
```
user_said = input("Mời bạn nhập lời nói: ")
print("Chatbot: " + user_said)
```
