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
# 11. Tính tổng giá trị
- Hàm **SUM()** tính tổng giá trị.
```
SELECT SUM(luong)
FROM nhan_vien
WHERE nam_lam = 2014
AND phong_ban = 'marketing';
```
# 12. 
