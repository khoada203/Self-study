# Mục lục
- [1. Sắp xếp các hàng với ORDER BY](#1-sắp-xếp-các-hàng-với-order-by)
- [2. Sắp xếp tăng dần và giảm dần](#2-sắp-xếp-tăng-dần-và-giảm-dần)
- [3. Sắp xếp theo một vài cột](#3-sắp-xếp-theo-một-vài-cột)
- [4. Sắp xếp có điều kiện](#4-sắp-xếp-có-điều-kiện)
- [5. Lọc trùng dữ liệu](#5-lọc-trùng-dữ-liệu)
- [6. Lọc trùng dữ liệu trên nhiều cột](#6-lọc-trùng-dữ-liệu-trên-nhiều-cột)
- [7. Đếm số hàng](#7-đếm-số-hàng)
- [8. Đếm số hàng không NULL](#8-đếm-số-hàng-không-null)
- [9. Đếm giá trị duy nhất trong một cột](#9-đếm-giá-trị-duy-nhất-trong-một-cột)
- [10. Giá trị lớn nhất và nhỏ nhất](#10-giá-trị-lớn-nhất-và-nhỏ-nhất)
- [11. Tính giá trị trung bình](#11-tính-giá-trị-trung-bình)
- [12. Tính tổng giá trị](#12-tính-tổng-giá-trị)
- [13. Kết hợp Group By và Count](#13-kết-hợp-group-by-và-count)
- [14. Kết hợp Group By và Min,Max](#14-kết-hợp-group-by-và-minmax)
- [15. Kết hợp Group By và Avg](#15-kết-hợp-group-by-và-avg)
- [16. Nhóm các hàng dựa trên nhiều cột](#16-nhóm-các-hàng-dựa-trên-nhiều-cột)
- [17. Lọc nhóm dữ liệu](#17-lọc-nhóm-dữ-liệu)
- [18. Sắp xếp các nhóm](#18-sắp-xếp-các-nhóm)

# 1. Sắp xếp các hàng với ORDER BY
```
SELECT *
FROM nhan_vien
ORDER BY luong;
```
# 2. Sắp xếp tăng dần và giảm dần
- ASC (viết tắt cho thứ tự ascending - tăng dần)
- DESC (viết tắt cho thứ tự descending - giảm dần)
```
SELECT *
FROM nhan_vien
ORDER BY ten DESC;
```
# 3. Sắp xếp theo một vài cột
```
SELECT *
FROM nhan_vien
ORDER BY phong_ban ASC, luong DESC;
```
# 4. Sắp xếp có điều kiện
```
SELECT *
FROM nhan_vien
WHERE nhan_vien.nam_lam = 2011
ORDER BY luong;
```
# 5. Lọc trùng dữ liệu
- Trước tên cột, chúng ta thêm từ **DISTINCT**
```
SELECT DISTINCT nam_lam
FROM nhan_vien;
```
# 6. Lọc trùng dữ liệu trên nhiều cột
```
SELECT DISTINCT
  nhan_vien.phong_ban,
  nhan_vien.chuc_vu
FROM nhan_vien;
```
# 7. Đếm số hàng
- Thay vì sử dụng dấu hoa thị tương đương với  'tất cả', chúng ta cung cấp biểu thức COUNT(*).
- **COUNT(*) là một hàm**
```
SELECT COUNT(*)
FROM nhan_vien;
```

# 8. Đếm số hàng không NULL
**Sự khác biệt giữa COUNT(*) và COUNT(chuc_vu) là gì?**
- Hàm đầu tiên đếm số hàng trong bảng và hàm thứ hai đếm số hàng trong đó cột **chuc_vu** có giá trị cụ thể.
- Nói cách khác, nếu có một giá trị **NULL** trong cột **chuc_vu**, hàng đó sẽ không được tính vào kết quả.

```
SELECT COUNT(chuc_vu) AS non_null_no
FROM nhan_vien;
```
# 9. Đếm giá trị duy nhất trong một cột
- Chúng ta cũng có thể thêm từ khóa DISTINCT vào trong hàm COUNT()
```
SELECT COUNT(DISTINCT chuc_vu) AS distinct_positions
FROM nhan_vien;
```
# 10. Giá trị lớn nhất và nhỏ nhất
- Hàm **MIN()** trả về giá trị nhỏ nhất.
- Hàm **MAX()** trả về giá trị lớn nhất.
```
SELECT MAX(luong)
FROM nhan_vien;
```

# 11. Tính giá trị trung bình
- Hàm **AVG()** tính giá trị trung bình của cột được chỉ định.
```
SELECT AVG(luong)
FROM nhan_vien
WHERE nam_lam = 2013;
```
# 12. Tính tổng giá trị
- Hàm **SUM()** tính tổng giá trị.
```
SELECT SUM(luong)
FROM nhan_vien
WHERE nam_lam = 2014
AND phong_ban = 'marketing';
```
# 13. Kết hợp Group By và Count
- Chúng ta nhập GROUP BY theo sau là tên cột. GROUP BY sẽ nhóm tất cả các hàng có cùng giá trị trong cột được chỉ định lại với nhau.
```
SELECT
  phong_ban,
  COUNT(*) AS so_nhan_vien
FROM nhan_vien
WHERE nam_lam = 2013
GROUP BY phong_ban;
```
# 14. Kết hợp Group By và Min,Max
```
SELECT
  phong_ban,
  MIN(luong),
  MAX(luong)
FROM nhan_vien
WHERE nam_lam = 2014
GROUP BY phong_ban;
```
# 15. Kết hợp Group By và Avg
```
SELECT
  phong_ban,
  AVG(luong)
FROM nhan_vien
WHERE nam_lam = 2015
GROUP BY phong_ban;
```
# 16. Nhóm các hàng dựa trên nhiều cột
```
SELECT
  ho,
  ten,
  AVG(luong)
FROM nhan_vien
GROUP BY ho, ten;
```
# 17. Lọc nhóm dữ liệu
- Chúng ta sử dụng từ khóa **HAVING**
- Lưu ý:
  + Trong SQL, các đoạn lệnh cụ thể luôn phải được đặt theo đúng thứ tự. Ví dụ, bạn không thể đặt WHERE trước FROM.
  + Tương tự, HAVING luôn phải đứng sau GROUP BY, không phải ngược lại.
## Bài tập 1:
```
SELECT
  ho,
  ten,
  COUNT(DISTINCT nam_lam) AS year
FROM nhan_vien
GROUP BY ho, ten
HAVING COUNT(DISTINCT nam_lam) > 2;
```
## Bài tập 2:
```
SELECT
  phong_ban,
  AVG(luong)
FROM nhan_vien
WHERE nam_lam = 2012
GROUP BY phong_ban
HAVING AVG(luong) > 3000000;
```
# 18. Sắp xếp các nhóm
- Các nhóm có thể được sắp xếp giống như các hàng.
```
SELECT
  ho,
  ten,
  SUM(luong)
FROM nhan_vien
GROUP BY ho, ten
ORDER BY SUM(luong) DESC;
```
