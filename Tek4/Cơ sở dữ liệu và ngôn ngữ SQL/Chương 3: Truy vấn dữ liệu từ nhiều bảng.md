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
# 8. Thực hành
**Bài tập 1:** 
- Đưa ra thông tin gồm tiêu đề và năm sản xuất từ bảng phim và cột ten và nam_sinh từ bảng dao_dien sao cho đầu ra hiển thị tên phim cùng với đạo diễn của phim.
- Đổi tên cột nam_sinh thành born_in. Chỉ chọn những bộ phim được quay bởi đạo diễn dưới 40 tuổi (tức là giá trị chênh lệch giữa nam_san_xuat và nam_sinh phải nhỏ hơn 40).
```
SELECT 
  phim.tieu_de,
  phim.nam_san_xuat,
  dao_dien.ten,
  dao_dien.nam_sinh AS born_in
FROM phim
JOIN dao_dien
  ON ma_dao_dien = dao_dien.id
WHERE (nam_san_xuat - nam_sinh) < 40;
```
**Bài tập 2:**
- Đưa ra thông tin gồm id, tieu_de và nam_san_xuat từ bảng phim và cột ten và nam_sinh từ bảng dao_dien sao cho đầu ra hiển thị tên phim cùng với đạo diễn của phim.
- Đổi tên cột nam_sinh thành born_in và tên cột nam_san_xuat thành produced_in. Và chỉ chọn những bộ phim thỏa mãn các điều kiện sau:
  + Có tên phim chứa một chữ cái 'a' và được quay sau năm 2000,
  + HOẶC được quay bởi đạo diễn sinh từ năm 1945 đến 1995.
```
SELECT 
  phim.id,
  phim.tieu_de,
  phim.nam_san_xuat AS produced_in,
  
  dao_dien.ten,
  dao_dien.nam_sinh AS born_in
  
FROM phim
JOIN dao_dien
  ON phim.ma_dao_dien = dao_dien.id

WHERE phim.tieu_de LIKE '%a%'
  AND phim.nam_san_xuat > 2000
  OR dao_dien.nam_sinh BETWEEN 1954 AND 1995;
```
