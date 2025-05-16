
# Mục lục
- [1. Trích xuất dữ liệu](#1-trích-xuất-dữ-liệu)
- [2. Lựa chọn một cột](#2-lựa-chọn-một-cột)
- [3. Lựa chọn nhiều cột](#3-lựa-chọn-nhiều-cột)
- [4. Chọn một vài hàng](#4-chọn-một-vài-hàng)
- [5. Toán tử điều kiện](#5-toán-tử-điều-kiện)
- [6. Toán tử không bằng (!=)](#6-toán-tử-không-bằng-)
- [7. Toán tử điều kiện và chọn cột](#7-toán-tử-điều-kiện-và-chọn-cột)
- [8. Toán tử Logic](#8-toán-tử-logic)
  - [8.1 OR](#81-or)
  - [8.2 AND](#82-and)
  - [8.3 NOT](#83-not)
- [9. Toán tử BETWEEN](#9-toán-tử-between)
- [10. Kết hợp nhiều điều kiện](#10-kết-hợp-nhiều-điều-kiện)
- [11. Dữ liệu văn bản](#11-dữ-liệu-văn-bản)
- [12. Ký hiệu phần trăm (%)](#12-ký-hiệu-phần-trăm-)
- [13. Ký hiệu gạch dưới](#13-ký-hiệu-gạch-dưới-)
- [14. Tìm các giá trị KHÔNG NULL và NULL](#14-tìm-các-giá-trị-không-null-và-null)
  - [14.1 Tìm giá trị KHÔNG NULL](#141-tìm-giá-trị-không-null)
  - [14.2 Tìm giá trị NULL](#142-tìm-giá-trị-null)
  - [14.3 So sánh với NULL](#143-so-sánh-với-null)
- [15. Các toán tử toán học cơ bản](#15-các-toán-tử-toán-học-cơ-bản)
- [16. Thực hành](#16-thực-hành)

# 1. Trích xuất dữ liệu
```
SELECT *
FROM xe;
```
# 2. Lựa chọn một cột
```
SELECT hang_xe
FROM xe;
```
# 3. Lựa chọn nhiều cột

```
SELECT
  loai_xe,
  gia
FROM xe;
```

# 4. Chọn một vài hàng
```
SELECT * <br>
FROM xe <br>
WHERE nam_san_xuat = 2022;
```
# 5. Toán tử điều kiện
- < (nhỏ hơn), > (lớn hơn), <= (nhỏ hơn hoặc bằng), >= (lớn hơn hoặc bằng).
```
SELECT * <br>
FROM xe <br>
WHERE gia > 1000000000;
```
# 6. Toán tử không bằng (!=)
- (!= hoặc đôi khi là <>)
```
SELECT *
FROM xe 
WHERE nam_san_xuat != 2021;
```

# 7. Toán tử điều kiện và chọn cột
```
SELECT
  hang_xe,
  loai_xe,
  nam_san_xuat
FROM xe 
WHERE gia <= 1300000000;
```

# 8. Toán tử Logic
## 8.1 OR
```
SELECT ma_xe
FROM xe 
WHERE nam_san_xuat < 2020
OR    gia < 700000000;
```

## 8.2 AND
```
SELECT ma_xe
FROM xe 
WHERE nam_san_xuat > 2020
AND   gia < 2000000000;
```
## 8.3 NOT
```
SELECT
  ma_xe,
  hang_xe,
  loai_xe
FROM xe 
WHERE nam_san_xuat NOT BETWEEN 2021 AND 2023;
```

# 9. Toán tử BETWEEN
```
SELECT
  ma_xe,
  hang_xe,
  loai_xe
FROM xe 
WHERE nam_san_xuat BETWEEN 2021 AND 2023;
```

# 10. Kết hợp nhiều điều kiện
- Sử dụng dấu ngoặc ()
```
SELECT ma_xe
FROM xe 
WHERE (nam_san_xuat < 2020 OR nam_san_xuat > 2022)
AND   (gia < 1000000000 OR gia > 3000000000);
```
# 11. Dữ liệu văn bản
- đặt văn bản trong dấu nháy đơn.
```
SELECT *
FROM xe 
WHERE hang_xe = 'Ford';
```
# 12. Ký hiệu phần trăm (%)
- Sử dụng khi không biết chính xác các chữ cái mà chúng ta đang tìm kiếm.
```
SELECT
  ma_xe,
  hang_xe,
  loai_xe
FROM xe 
WHERE hang_xe LIKE 'H%';
```
--> Đưa ra mã xe, hãng xe, loại xe của những xe bắt đầu bằng chữ H.

**Ví dụ 2:**
```
SELECT *
FROM user
WHERE name LIKE '%A%';
```
--> Ví dụ trên sẽ chọn bất kỳ người dùng nào có tên chứa ít nhất một chữ 'A'.

# 13. Ký hiệu gạch dưới
- Ký hiệu gạch dưới (_) có thể khớp chính xác một ký tự.
```
SELECT *
FROM xe 
WHERE hang_xe LIKE 'Volk_wagen';
```

# 14. Tìm các giá trị KHÔNG NULL và NULL
## 14.1 Tìm giá trị KHÔNG NULL
- Sử dụng IS NOT NULL
```
SELECT *
FROM xe 
WHERE gia IS NOT NULL;
```
## 14.2 Tìm giá trị NULL
- Sử dụng IS NULL
```
SELECT *
FROM xe
WHERE gia IS NULL;
```
## 14.3 So sánh với NULL
- **NULL** là một giá trị đặc biệt. Nó có nghĩa là một số thông tin bị **thiếu** hoặc **không xác định**.
- NULL không bao giờ bằng 0. Nên vì thế biểu thức NULL = NULL sẽ không bao giờ đúng trong SQL!

# 15. Các toán tử toán học cơ bản
- cộng (+), trừ (-), nhân (*) và chia (/)
```
SELECT *
FROM xe 
WHERE (gia * 0.2) > 1000000000;
```

# 16. Thực hành
Chọn các cột của những xe hơi:
- Được sản xuất từ năm 2009 đến năm 2021,
- Không phải là hãng VinFast,
- Tên loại xe bắt đầu bằng 'P' hoặc 'F',
- Và cuối cùng là có giá xe niêm yết.
```
SELECT *
FROM xe 
WHERE (nam_san_xuat BETWEEN 2009 AND 2021)
AND (hang_xe != 'VinFast')
AND (loai_xe LIKE 'P%' OR loai_xe LIKE 'F%')
AND (gia IS NOT NULL);
```
