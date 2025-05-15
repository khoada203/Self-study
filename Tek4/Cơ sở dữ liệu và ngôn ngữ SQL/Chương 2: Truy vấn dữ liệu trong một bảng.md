# 1. Trích xuất dữ liệu
SELECT *
FROM xe;

# 2. Lựa chọn một cột
SELECT hang_xe
FROM xe;

# 3. Lựa chọn nhiều cột
SELECT
  loai_xe,
  gia
FROM xe;

# 4. Chọn một vài hàng
SELECT *
FROM xe 
WHERE nam_san_xuat = 2022;

# 5. Toán tử điều kiện
- < (nhỏ hơn), > (lớn hơn), <= (nhỏ hơn hoặc bằng), >= (lớn hơn hoặc bằng).
SELECT *
FROM xe 
WHERE gia > 1000000000;

<span style="color: blue;">
SELECT *
FROM xe 
WHERE gia > 1000000000;
</span>
