# Mục lục

# 1. Trích xuất dữ liệu từ nhiều bảng
```
SELECT *
FROM phim, dao_dien;
```
# 2. Kết hợp các bảng dựa trên điều kiện
```
SELECT *
FROM phim, dao_dien
WHERE phim.ma_dao_dien = dao_dien.id;
```
# 3. Sử dụng JOIN để kết hợp các bảng
```
SELECT *
FROM phim
JOIN dao_dien
ON   phim.ma_dao_dien = dao_dien.id;
```
# 4. Trích xuất cột cụ thể
```
SELECT
  phim.tieu_de,
  dao_dien.ten
FROM phim
JOIN dao_dien
  ON phim.ma_dao_dien = dao_dien.id;
```
# 5. Tham chiếu đến cột mà không sử dụng tên bảng
- Nếu tên của cột là duy nhất thì bạn có thể bỏ qua tên bảng.
```
SELECT
  ten,
  tieu_de
FROM dao_dien
JOIN phim
  ON dao_dien.id = ma_dao_dien;
```
# 6. Đổi tên cột bằng từ khóa AS
- Tên mới chỉ là bí danh, nghĩa là nó là tên tạm thời và không thay đổi tên thực tế trong cơ sở dữ liệu.
- Nó chỉ ảnh hưởng đến cách cột được hiển thị trong kết quả của truy vấn.
```
SELECT 
  phim.tieu_de AS ten_phim,
  ten
FROM phim
JOIN dao_dien
  ON ma_dao_dien = dao_dien.id;
```
# 7. Chọn lọc dữ liệu từ các bảng kết hợp
**Ví dụ 1**
```
SELECT *
FROM phim
JOIN dao_dien
  ON phim.ma_dao_dien = dao_dien.id 
WHERE phim.nam_san_xuat > 2015;
```

**Ví dụ 2**
```
SELECT *
FROM phim
JOIN dao_dien
  ON phim.ma_dao_dien = dao_dien.id 
WHERE dao_dien.ten = 'Joe Russo'
```
